---
name: Read a patient's clinical record from Epic (patient-context SMART app)
description: Authorize a patient-facing SMART on FHIR app against an Epic FHIR R4 endpoint and read the authorized patient's problems, medications, allergies, labs and documents.
api: fhir/epic-fhir-r4-capabilitystatement.json
fhir_version: 4.0.1
operations:
  - Patient.Read
  - Condition.Search
  - MedicationRequest.Search
  - AllergyIntolerance.Search
  - Observation.Search
  - DocumentReference.Search
method: generated
generated: '2026-08-14'
source: fhir/epic-fhir-r4-capabilitystatement.json + fhir/epic-fhir-r4-smart-configuration.json
---

# Read a patient's record from Epic

Every operation below is advertised in the harvested R4 sandbox CapabilityStatement.
Do not call an interaction that is not advertised for a resource type — Epic returns
HTTP 405 with issue code `not-supported`.

## 1. Resolve the endpoint before anything else

There is no single Epic production base URL. Each health system runs its own instance.
Resolve the customer's FHIR base from the published endpoint directory
(`fhir/epic-systems-endpoint-catalog.yml`, 479 R4 endpoints) or ask the user which
organization they are connecting to. For development use the sandbox base:

```
https://fhir.epic.com/interconnect-fhir-oauth/api/FHIR/R4
```

## 2. Authorize with SMART standalone launch

Use `authorization_endpoint` / `token_endpoint` from
`.well-known/smart-configuration` (captured at `fhir/epic-fhir-r4-smart-configuration.json`).
PKCE is required — `code_challenge_methods_supported` is `[S256]`.

- Request `launch/patient openid fhirUser offline_access` plus the `patient/*.read`
  scopes for the resources you will touch.
- The token response carries the `patient` context. Use that FHIR ID; never let the
  user supply a patient ID in patient context.
- Send `Authorization: Bearer <access_token>` on every call.

Sandbox test identity (published by Epic): MyChart `fhircamila` / `epicepic1`,
patient FHIR ID `erXuFYUfucBZaryVksYEcMg3`. See `sandbox/epic-systems-sandbox.yml`.

## 3. Read the record

| Step | Call | Notes |
|---|---|---|
| Demographics | `GET Patient/{id}` (`Patient.Read`) | `id` is the token's `patient` claim |
| Problems | `GET Condition?patient={id}&category=problem-list-item` | `category` is required — omitting it returns error `59108` |
| Medications | `GET MedicationRequest?patient={id}` | invalid `category` values return `59101` |
| Allergies | `GET AllergyIntolerance?patient={id}` | |
| Labs | `GET Observation?patient={id}&category=laboratory` | `category` required; a bad value returns `59111` |
| Vitals | `GET Observation?patient={id}&category=vital-signs` | |
| Documents | `GET DocumentReference?patient={id}` | daily query ceiling — see step 5 |

## 4. Page correctly

`search-type` returns a searchset `Bundle`. Request page size with `_count` and follow
`Bundle.link[relation=next].url` — never construct offsets. Cached search sessions
expire: error `4113` means the paging session is gone and the original search must be
re-issued. If the query string is long, POST to `{resource}/_search` with
`Content-Type: application/x-www-form-urlencoded`; from the February 2026 Epic version
query-string parameters other than `_format` are IGNORED on that endpoint, so send
parameters in the body only.

## 5. Handle Epic's error semantics, not just HTTP

Errors arrive as a FHIR `OperationOutcome` (`application/fhir+json`), not RFC 9457
problem+json. Read `issue[].severity` and the Epic numeric code
(`errors/epic-systems-error-codes.yml`):

- `4101` warning — valid request, no data documented. This is **not** an error; render "none recorded".
- `4119` warning — additional data may exist beyond what a patient-context app can see. Say so; do not imply completeness.
- `4127` fatal — Patient.Search exceeded 100 results. Narrow the search; do not page past it.
- `4118` fatal — the authenticated user is not allowed this data. Do not retry.
- `4130` / `4131` / `4134` — Break-the-Glass restriction on a sensitive chart. This is a policy outcome, not a transient failure. Never retry, never work around it.
- `4135` fatal — the daily document-query maximum is reached. Stop for the day; retrying will not help.

## 6. Do not overstate what you read

In a patient-facing context Epic filters responses: data not yet reconciled by a
clinician may be withheld, patient-friendly medication names may be substituted for
the coded name, and specific lab results may be excluded for state or local
regulatory reasons. Filtering is configured per health system. Present results as
"what this portal exposes", never as the complete medical record.
