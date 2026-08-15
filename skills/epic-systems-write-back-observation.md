---
name: Write data back into an Epic chart
description: File patient-generated readings, allergies, conditions and clinical documents into an Epic chart using the eleven R4 resources that actually advertise create.
api: fhir/epic-fhir-r4-capabilitystatement.json
fhir_version: 4.0.1
operations:
  - Observation.Create
  - AllergyIntolerance.Create
  - Condition.Create
  - DocumentReference.Create
  - Procedure.Create
  - ServiceRequest.Create
  - QuestionnaireResponse.Create
  - Communication.Create
  - BodyStructure.Create
  - ConceptMap.Create
  - Patient.Create
method: generated
generated: '2026-08-14'
source: fhir/epic-fhir-r4-capabilitystatement.json
---

# Write back into Epic

## 1. Know how small the write surface is

Of the 59 R4 resource types Epic advertises, **59 support read, 56 support search-type,
but only 11 support create and 7 support update.** Check the CapabilityStatement before
you attempt a write; an unadvertised interaction returns HTTP 405 with issue code
`not-supported`, and no amount of retrying changes that.

Create is advertised on: `AllergyIntolerance`, `BodyStructure`, `Communication`,
`ConceptMap`, `Condition`, `DocumentReference`, `Observation`, `Patient`, `Procedure`,
`QuestionnaireResponse`, `ServiceRequest`.

Update is advertised on: `BodyStructure`, `DiagnosticReport`, `DocumentReference`,
`Observation`, `Procedure`, `ServiceRequest`, `Task`.

## 2. Filing an Observation is a mapping problem, not an API problem

`Observation.Create` writes into an Epic **flowsheet row**, and that row must already
be built and mapped on the customer's system. Three published errors all mean "the
build is missing", not "your request is malformed":

- `59187` — in a patient-facing app, the patient has no Patient-Entered Flowsheets assigned.
- `59188` — no single flowsheet row matches the codes you sent, or the row found is not mapped to the vital-sign LOINC code (`8716-3`).
- `59189` — the reading failed to file.

The fix for all three is configuration work with the health system, before go-live.
Send LOINC codes the customer has mapped. Do not retry on these.

## 3. Duplicates are rejected, so writes are not blindly idempotent

`59141` — "An attempt was made to create a duplicate record" — is returned when, for
example, `AllergyIntolerance.Create` adds an allergy already on the chart. There is no
`Idempotency-Key` header on this API and the R4 CapabilityStatement does **not**
advertise `conditionalCreate` (`If-None-Exist`), so a retried POST is not safe by
construction. Before retrying a create whose response you did not see, search for the
resource you were writing and only re-POST if it is absent.

## 4. Updates ARE idempotent — use them that way

`PUT {base}/{Type}/{id}` is idempotent per FHIR/HTTP semantics and safe to retry.
Responses carry an `ETag` (`W/"vid"`); send `If-Match` with it on conditional writes so
a concurrent edit fails with `412` rather than silently overwriting a clinician.
See `conventions/epic-systems-conventions.yml`.

## 5. Validation errors tell you which element

The `591xx` family names the offending element:

- `59105` — structural failure, e.g. invalid JSON syntax.
- `59108` — required `{element}` missing.
- `59109` — optional `{element}` invalid (informational; the call may still succeed).
- `59111` — required `{element}` invalid.
- `59159` — content failed a business rule.
- `59177` — unexpected internal error (e.g. failed to file the LDA).
- `40000` — an incoming table mapping is missing on the customer's system.

Full registry: `errors/epic-systems-error-codes.yml`.

## 6. Scope and consequence

Writes need write scopes (`patient/Observation.write`, `user/Condition.write`, …) and,
in provider context, a user whose Epic security allows the action. A write into a chart
is a clinical action with a real audit trail. Never write speculative or inferred
clinical data, never write on a user's behalf without explicit confirmation of the
exact values, and surface `59141` duplicates to the user rather than resolving them
automatically.
