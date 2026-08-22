# Epic Systems (epic-systems)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Epic Systems Corporation is a privately held electronic health record (EHR/EMR) software company founded in 1979 and headquartered in Verona, Wisconsin, United States. Its "Epic on FHIR" developer program (fhir.epic.com / open.epic.com) exposes a standards-based HL7 FHIR interoperability surface for patient- and provider-facing apps, with live public sandbox endpoints across FHIR R4 (4.0.1), STU3 (3.0.1), and DSTU2 (1.0.2), SMART on FHIR / OAuth 2.0 authorization, FHIR Bulk Data ($export), and CDS Hooks. Epic is a core node of the U.S. healthcare interoperability landscape shaped by the ONC/CMS 21st Century Cures Act information-blocking rules and TEFCA.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/epic-systems/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/epic-systems/refs/heads/main/apis.yml)

## Tags

- Healthcare
- United States
- EHR
- EMR
- FHIR
- HL7
- Interoperability
- SMART on FHIR
- US Core
- Clinical Data

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Epic FHIR R4 API

Epic's HL7 FHIR R4 (4.0.1) REST API, aligned to the US Core implementation guides, exposing 59 resource types with read, search, create, and update interactions, authorized with SMART on FHIR / OAuth 2.0.

- **Human URL:** [https://fhir.epic.com/Specifications](https://fhir.epic.com/Specifications)
- **Base URL:** `https://fhir.epic.com/interconnect-fhir-oauth/api/FHIR/R4`

#### Properties

- [CapabilityStatement](fhir/epic-fhir-r4-capabilitystatement.json) — harvested verbatim from the live R4 `metadata` endpoint
- [SMART Configuration](fhir/epic-fhir-r4-smart-configuration.json)
- [Documentation](https://fhir.epic.com/Documentation?docId=fhirtutorial)
- [API Reference](https://fhir.epic.com/Specifications)
- [Authentication](https://fhir.epic.com/Documentation?docId=oauth2)

### Epic FHIR STU3 API

Epic's HL7 FHIR STU3 (3.0.1) REST API for clinical and administrative resources, authorized with SMART on FHIR / OAuth 2.0.

- **Human URL:** [https://fhir.epic.com/Specifications](https://fhir.epic.com/Specifications)
- **Base URL:** `https://fhir.epic.com/interconnect-fhir-oauth/api/FHIR/STU3`

#### Properties

- [CapabilityStatement](fhir/epic-fhir-stu3-capabilitystatement.json) — harvested verbatim
- [Documentation](https://fhir.epic.com/Documentation?docId=fhirtutorial)
- [API Reference](https://fhir.epic.com/Specifications)

### Epic FHIR DSTU2 API

Epic's HL7 FHIR DSTU2 (1.0.2) REST API, published as a FHIR Conformance resource covering the legacy DSTU2 resource set.

- **Human URL:** [https://fhir.epic.com/Specifications](https://fhir.epic.com/Specifications)
- **Base URL:** `https://fhir.epic.com/interconnect-fhir-oauth/api/FHIR/DSTU2`

#### Properties

- [Conformance](fhir/epic-fhir-dstu2-conformance.json) — harvested verbatim
- [Documentation](https://fhir.epic.com/Documentation?docId=fhirtutorial)
- [API Reference](https://fhir.epic.com/Specifications)

### Epic SMART on FHIR Authorization

Epic's SMART on FHIR / OAuth 2.0 authorization surface backing the FHIR APIs, with EHR and standalone launch, confidential/asymmetric clients, OpenID Connect, and SMART v1/v2 permission scopes.

- **Human URL:** [https://fhir.epic.com/Documentation?docId=oauth2](https://fhir.epic.com/Documentation?docId=oauth2)
- **Base URL:** `https://fhir.epic.com/interconnect-fhir-oauth/oauth2`

#### Properties

- [SMART Configuration](fhir/epic-fhir-r4-smart-configuration.json) — harvested verbatim
- [Documentation](https://fhir.epic.com/Documentation?docId=oauth2)
- [Authentication](authentication/epic-systems-authentication.yml)

### Epic FHIR Bulk Data Access API

Epic's implementation of the HL7 FHIR Bulk Data Access (Flat FHIR) `$export` operation for backend, system-level population export, authorized with OAuth 2.0 client-credentials (asymmetric client authentication).

- **Human URL:** [https://fhir.epic.com/Documentation?docId=bulkdataaccesstutorial](https://fhir.epic.com/Documentation?docId=bulkdataaccesstutorial)
- **Base URL:** `https://fhir.epic.com/interconnect-fhir-oauth/api/FHIR/R4`

### Epic CDS Hooks API

Epic's support for the CDS Hooks specification, letting external clinical decision support services return cards and SMART app launch links at documented workflow hook points inside the Epic EHR.

- **Human URL:** [https://fhir.epic.com/Documentation?docId=cdshookstutorial](https://fhir.epic.com/Documentation?docId=cdshookstutorial)

## Common Properties

- [Website](https://www.epic.com/)
- [Developer Portal](https://fhir.epic.com/)
- [Documentation](https://fhir.epic.com/Documentation)
- [API Reference](https://fhir.epic.com/Specifications)
- [Getting Started](https://fhir.epic.com/Documentation?docId=fhirtutorial)
- [Authentication](authentication/epic-systems-authentication.yml)
- [Sign Up / Client Registration](https://fhir.epic.com/Developer/Index)
- [Terms of Service (API License Agreement)](https://fhir.epic.com/Download/ApiLicenseAgreement)
- [LinkedIn](https://www.linkedin.com/company/epic1979/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
