# OSCAR EMR (oscar-emr)

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

OSCAR EMR is an open-source electronic medical record system created by Dr. David Chan and McMaster University's Department of Family Medicine, and one of Canada's most widely deployed primary-care EMRs. The core software is licensed GPL v2+ (mirrored at scoophealth/oscar on GitHub and on Bitbucket), while the commercially supported **OSCAR Pro** distribution is delivered by the WELL EMR Group (a WELL Health company) to 2,000+ clinics and 10,000+ providers across Canada.

OSCAR exposes a documented REST web-services API and, as self-hosted software, is realized per-clinic rather than as a single hosted platform. Legacy clinical data flows use HL7 v2 messaging, and OSCAR ships an internal HL7 FHIR integration used for Ontario public-health and immunization reporting.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/oscar-emr/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/oscar-emr/refs/heads/main/apis.yml)

## Tags

- Healthcare
- Canada
- EHR
- EMR
- Primary Care
- Open Source
- FHIR
- HL7
- Interoperability
- SMART on FHIR
- OAuth

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### OSCAR REST Web Services API

OSCAR's REST web-services layer, served under the `/ws/services` base path of a deployed OSCAR instance, covering most of the clinical record — scheduling/appointments, demographics, billing, prescriptions, documents, labs, ticklers, eForms and providers. Applications register as REST clients through the OSCAR Administration interface and authenticate provider users with 3-legged **OAuth 1.0a** (`/ws/oauth/initiate`, `/ws/oauth/authorize`, `/ws/oauth/token`). Because OSCAR is self-hosted, the host and web context are deployment-specific (documented example: `http://localhost:8080/oscar_15/ws/services`), so no single public base URL exists. Runtime documentation is generated with RAML (RAML for JAX-RS + MuleSoft API Console) rather than OpenAPI/Swagger; no static downloadable spec is published.

- **Human URL:** [Connecting to OSCAR's REST API](https://oscaremr.atlassian.net/wiki/spaces/OS/pages/79855638/Connecting+to+OSCAR's+REST+API)

#### Tags

- EHR
- EMR
- REST
- Primary Care
- Canada

#### Properties

- [Documentation](https://oscaremr.atlassian.net/wiki/spaces/OS/overview)
- [API Reference](https://oscaremr.atlassian.net/wiki/spaces/OS/pages/85396074/Documenting+the+REST+API)
- [Getting Started](https://oscaremr.atlassian.net/wiki/spaces/OS/pages/79855638/Connecting+to+OSCAR's+REST+API)
- [Authentication (OAuth 1.0a)](https://oscaremr.atlassian.net/wiki/spaces/OS/pages/79855638/Connecting+to+OSCAR's+REST+API)

## FHIR & HL7 Posture

- **HL7 v2** — legacy clinical messaging for labs and documents.
- **HL7 FHIR** — internal outbound integration (`org.oscarehr.integration.fhir`) for Ontario public-health / immunization reporting to registries such as **BORN** and **DHIR**. Not a hosted, consumable FHIR REST server; there is no `/metadata` CapabilityStatement or `/.well-known/smart-configuration` published.
- **SMART on FHIR / OAuth2** — marketed for OSCAR Pro third-party integrations via the apps.health marketplace, but partner-gated and not publicly documented.

## Common Properties

- [Website](https://oscar-emr.com/)
- [Developer Portal](https://oscaremr.atlassian.net/wiki/spaces/OS/overview)
- [Documentation](https://oscaremr.atlassian.net/wiki/spaces/OS/overview)
- [API Reference](https://oscaremr.atlassian.net/wiki/spaces/OS/pages/85396074/Documenting+the+REST+API)
- [Getting Started](https://oscaremr.atlassian.net/wiki/spaces/OS/pages/79855638/Connecting+to+OSCAR's+REST+API)
- [GitHub Organization](https://github.com/scoophealth)
- [Source Code (Bitbucket)](https://bitbucket.org/oscaremr/oscar/src/stable/)
- [Marketplace (apps.health)](https://apps.health/)
- [Sign Up (OSCAR Pro)](https://share.hsforms.com/1p6l4kFOyRh6_7RfxVHpYTQcgcz4)
- [Support](mailto:help@oscarprodesk.ca)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
