# Epic Systems

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

Epic Systems Corporation is a privately held electronic health record (EHR/EMR) software company founded in 1979 and headquartered in Verona, Wisconsin, United States. Epic's software supports the medical records of a large share of U.S. hospital systems and academic medical centers, and its "Epic on FHIR" developer program (fhir.epic.com / open.epic.com) exposes a standards-based HL7 FHIR interoperability surface for patient- and provider-facing apps. Epic serves live, public sandbox FHIR endpoints across three FHIR versions - R4 (4.0.1), STU3 (3.0.1), and DSTU2 (1.0.2) - aligned to the US Core implementation guides, with SMART on FHIR / OAuth 2.0 authorization, CDS Hooks, and FHIR Bulk Data ($export) access. Production access requires client registration and a health system's participation; the developer sandbox, specifications, and CapabilityStatements are openly published. Epic is a core node of the U.S. healthcare interoperability landscape shaped by the ONC/CMS 21st Century Cures Act information-blocking rules and TEFCA.

**Areas:** Healthcare · United States · Electronic Health Records · FHIR · HL7 · Interoperability · SMART on FHIR · US Core · Clinical Data

## Epic Systems on APIs.io

Everything profiled for Epic Systems is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/epic-systems/](https://apis.io/providers/epic-systems/)** — or go straight to one of the APIs or properties below.

### APIs (6)

- [Epic FHIR R4 API](https://apis.io/apis/epic-systems/epic-fhir-r4-api/) — Epic's HL7 FHIR R4 (4.0.1) REST API, aligned to the US Core implementation guides and exposing 59 resource types (Patient, Encounter, Observation,…
- [Epic FHIR STU3 API](https://apis.io/apis/epic-systems/epic-fhir-stu3-api/) — Epic's HL7 FHIR STU3 (3.0.1) REST API for clinical and administrative resources, authorized with SMART on FHIR / OAuth 2.0. A live public sandbox…
- [Epic FHIR DSTU2 API](https://apis.io/apis/epic-systems/epic-fhir-dstu2-api/) — Epic's HL7 FHIR DSTU2 (1.0.2) REST API, published as a FHIR Conformance resource covering the legacy DSTU2 resource set. A live public sandbox Conformance…
- [Epic SMART on FHIR Authorization](https://apis.io/apis/epic-systems/epic-smart-on-fhir-authorization/) — Epic's SMART on FHIR / OAuth 2.0 authorization surface backing the FHIR APIs. The live .well-known/smart-configuration advertises authorize/token endpoints,…
- [Epic FHIR Bulk Data Access API](https://apis.io/apis/epic-systems/epic-fhir-bulk-data-api/) — Epic's implementation of the HL7 FHIR Bulk Data Access (Flat FHIR) specification, providing backend system-level population export via the $export…
- [Epic CDS Hooks API](https://apis.io/apis/epic-systems/epic-cds-hooks-api/) — Epic's support for the CDS Hooks specification, letting external clinical decision support services return cards and SMART app launch links at documented…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Epic Systems Cds Hooks Webhooks](https://apis.io/asyncapis/epic-systems/epic-systems-cds-hooks-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [epic-systems-mcp.yml](https://apis.io/servers/epic-systems/epic-systems-mcp-yml/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Epic Systems Authentication](https://apis.io/security/epic-systems/epic-systems-authentication/)
- [Epic Systems Domain Security](https://apis.io/security/epic-systems/epic-systems-domain-security/)
- [Epic Systems Vulnerability Disclosure](https://apis.io/security/epic-systems/epic-systems-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Epic Systems Scopes](https://apis.io/scopes/epic-systems/epic-systems-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Epic Systems Plans Pricing](https://apis.io/plans/epic-systems/epic-systems-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Epic Systems Rate Limits](https://apis.io/rate-limits/epic-systems/epic-systems-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.epic.com/)
- [Documentation](https://fhir.epic.com/Documentation)
- [Getting started](https://fhir.epic.com/Documentation?docId=fhirtutorial)
- [API reference](https://fhir.epic.com/Specifications)
- [Pricing](https://fhir.epic.com/Documentation?docId=cms_prior_auth_playbook)
- [Sign up](https://fhir.epic.com/Developer/Index)
- [Support](https://open.epic.com/Home/Contact)
- [Blog](https://www.epic.com/epic/newsroom/)
- [Security](https://www.epic.com/epic/page/reporting-potential-security-vulnerability/)
- [Terms of service](https://fhir.epic.com/Download/ApiLicenseAgreement)
- [Privacy policy](https://www.epic.com/privacypolicies/)

## API Evangelist rating

**Kin Score 62.5** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 44.2 |
| Contract governance | 18.2 |
| Operational transparency | 73.7 |
| Developer ergonomics | 66.1 |
| Access clarity | 65.8 |

**Agent readiness 37.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 48.4** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/epic-systems/](https://apis.io/providers/epic-systems/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Epic Systems: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/epic-systems/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
