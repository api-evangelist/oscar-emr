# OSCAR EMR (oscar-emr)

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
