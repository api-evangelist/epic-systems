# Epic Systems (epic-systems)

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
