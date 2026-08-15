---
name: Export a population from Epic with FHIR Bulk Data
description: Authenticate a backend service with client-credentials + private_key_jwt and run a Group $export against an Epic FHIR R4 endpoint, then poll and fetch the NDJSON files.
api: fhir/epic-fhir-r4-capabilitystatement.json
fhir_version: 4.0.1
operations:
  - Group.$group-export
  - Patient.Search
  - Immunization.Search
method: generated
generated: '2026-08-14'
source: fhir/epic-fhir-r4-capabilitystatement.json (instantiates http://hl7.org/fhir/uv/bulkdata/CapabilityStatement/bulk-data)
---

# Bulk-export a population from Epic

The R4 CapabilityStatement declares `instantiates:
http://hl7.org/fhir/uv/bulkdata/CapabilityStatement/bulk-data`, and `Group` advertises
the `group-export` operation. That is the grounding for this skill.

## 1. Register the app with all four bulk APIs

Epic gates the bulk surface on app registration, not just scope at runtime. The
registered app must select **all four**:

- Bulk Data Kick-off
- Bulk Data Status Request
- Bulk Data File Request
- Bulk Data Delete Request

…plus the **Search** interaction of every resource you intend to export. Exporting
demographics and immunizations means also selecting `Patient.Search (R4)` and
`Immunization.Search (R4)`. Miss one and the export returns nothing useful.

In the sandbox, registering all four automatically grants access to Epic's published
test Group `e3iabhmS8rsueyz7vaimuiaSmfGvi.QwjVXJANlPOgR83`.

## 2. Authenticate as a backend service

Use the SMART Backend Services flow — `client_credentials` with
`private_key_jwt` asymmetric client authentication. There is no client secret and no
user in this flow.

**Key handling has a hard deadline.** Static `.pem` public keys are being retired:
they stopped being accepted for new sandbox uploads in the August 2025 Epic version,
stopped working in the sandbox in February 2026, and stopped working in customer
environments in the May 2026 version. Host a **JWK Set URL (JKU)**. Use different
JKUs for non-production and production — Epic requires it — and include `kid` in both
the JWK Set and the JWT header so Epic can select the right key.
See `changelog/epic-systems-changelog.yml`.

## 3. Kick off, poll, fetch, delete

```
POST {base}/Group/{groupId}/$export
Authorization: Bearer <access_token>
Accept: application/fhir+json
Prefer: respond-async
```

- A successful kick-off returns `202 Accepted` with a `Content-Location` polling URL.
- Poll that URL. Keep polling until it returns `200` with a manifest of `output[]`
  NDJSON file URLs. Respect any `Retry-After` on the polling response — this is the
  one place in the Epic surface where a retry interval is conveyed at runtime.
- Fetch each `output[].url` with the same bearer token. Files are NDJSON, one resource
  per line.
- Call the delete request on the polling URL when done. Do not leave completed jobs
  sitting on the customer's system.

## 4. Stay inside the customer's budget

Epic's App Developer Guidelines require an app to consume no more than **1%** of the
customer's operational database resources at peak (07:00–19:00 local, varies by site)
and **5%** off-peak, and require apps making significant API volume to provide their
own guardrails and throttling. Schedule exports off-peak, one job at a time, and never
run a bulk export in a loop. There is no rate-limit header to tell you when you are
too close — see `rate-limits/epic-systems-rate-limits.yml`.

## 5. Sandbox etiquette

Bound any recurring schedule to about a week and disable it once validated. Do not
iterate every record in the sandbox; export the published test Group.
