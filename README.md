# Green Button Alliance (green-button-alliance)

The Green Button Alliance (GBA) is the non-profit that stewards, tests and certifies the Green Button standard — the NAESB REQ.21 Energy Services Provider Interface (ESPI) profile for utility customer electricity, natural gas and water usage data, in its Download My Data (DMD) and Connect My Data (CMD) forms. Incorporated in North Carolina and headquartered at PO Box 268, Jamison, Pennsylvania, it was formed after the 2012 White House / U.S. Department of Energy / NIST call to action and is the industry's only source of Green Button certification (Data Custodian DMD $3,000, CMD $3,200, membership not required), alongside a free public Directory Services listing of utilities, third-party apps and platform providers. GBA sits in the standards-and-certification layer of the United States energy value chain, above the investor-owned utilities and the energy-data platforms (UtilityAPI, Con Edison and Enbridge Gas are sponsor members) that actually move consumer data. Its API posture is contracts without a service: two real OpenAPI 3.x definitions of the CMD ESPI resource server are published free under Apache 2.0 on GitHub, but the normative ESPI v4.0 standard itself must be purchased from NAESB, GBA operates no production consumer-data or market-data API of its own, and its ESPI sandbox at sandbox.greenbuttonalliance.org:8443 is offline pending a replacement platform expected 2026Q3. Green Button in the United States is voluntary — there is no federal mandate — with obligation arriving only through state action and, outside the US, Ontario's O. Reg. 633/21.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/green-button-alliance/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/green-button-alliance/refs/heads/main/apis.yml)

## Tags

- Energy
- United States
- Utilities
- Electricity
- Gas
- Water
- Smart Metering
- Green Button
- ESPI
- Standards Body
- Certification
- Consumer Energy Data

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### Green Button Connect My Data (CMD) ESPI Resource Server API

The Green Button Connect My Data resource server API as specified by the Green Button Alliance against NAESB REQ.21 ESPI 4.0 — read access to ApplicationInformation, Authorization, UsagePoint and bulk Batch resources under `/espi/1_1/resource`, returned as ESPI/Atom XML and protected by OAuth 2.0 (authorization code and client credentials). GBA publishes the contract openly under Apache 2.0 on GitHub; the only base URL documented in it is GBA's own ESPI sandbox, which returned HTTP 403 to anonymous probes on 2026-07-27 and which GBA states is unavailable pending a new platform in 2026Q3. This is a specification of the interface every certified Data Custodian implements, not a live service run by GBA.

- **Human URL:** [https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/API/](https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/API/)
- **Base URL:** `https://sandbox.greenbuttonalliance.org:8443/DataCustodian`

#### Tags

- Green Button
- Connect My Data
- ESPI
- Energy
- Usage Data
- OAuth 2.0

#### Properties

- [OpenAPI](openapi/green-button-alliance-green-button-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/green-button-alliance-application-information-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/API/)
- [Documentation](https://www.greenbuttonalliance.org/green-button-connect-my-data-cmd)
- [Documentation](https://www.greenbuttonalliance.org/developer-resources)
- [Repository](https://github.com/GreenButtonAlliance/OpenAPI-Green-Button-Documentation)
- [Repository](https://github.com/GreenButtonAlliance/OpenESPI-DataCustodian-java)
- [Specification](https://www.naesb.org/espi_standards.asp)

### Green Button Third Party (OpenESPI) API

The Third Party side of the OpenESPI reference implementation — ApplicationInformation, Authorization and RetailCustomer operations documented as legacy Swagger 1.2 resource listings served from GBA's GitHub Pages site. The documented base path is `https://services.greenbuttondata.org/ThirdParty`, which returned HTTP 200 with an empty body on 2026-07-27. No OpenAPI 3.x definition of this surface was found and no live, callable service was confirmed; listed here because the documentation is genuinely published and reachable.

- **Human URL:** [https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/ThirdParty/](https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/ThirdParty/)
- **Base URL:** `https://services.greenbuttondata.org/ThirdParty`

#### Tags

- Green Button
- Third Party
- ESPI
- Energy
- Reference Implementation

#### Properties

- [API Reference](https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/ThirdParty/)
- [Repository](https://github.com/GreenButtonAlliance/OpenESPI-ThirdParty-java)
- [Repository](https://github.com/GreenButtonAlliance/OpenESPI-Common-java)

## Common Properties

- [Website](https://www.greenbuttonalliance.org/)
- [About](https://www.greenbuttonalliance.org/about-us)
- [Documentation](https://www.greenbuttonalliance.org/developer-resources)
- [Documentation](https://www.greenbuttonalliance.org/technical-info)
- [API Reference](https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/API/)
- [OpenID Connect](https://www.greenbuttonalliance.org/.well-known/openid-configuration) — member single sign-on discovery, not energy data
- [Certification](https://www.greenbuttonalliance.org/testing)
- [Certification](https://www.greenbuttonalliance.org/offerings/certification)
- [Directory](https://www.greenbuttonalliance.org/directory-services)
- [Specification](https://www.greenbuttonalliance.org/purchase-the-standard)
- [Specification](https://www.naesb.org/espi_standards.asp)
- [Sandbox](https://www.greenbuttonalliance.org/sandbox) — unavailable until 2026Q3
- [Tools](https://dmdvalidator.greenbuttonalliance.org/) — Green Button DMD Validator
- [GitHub Organization](https://github.com/GreenButtonAlliance)
- [LinkedIn](https://www.linkedin.com/company/green-button-alliance)
- [Blog](https://www.greenbuttonalliance.org/news)
- [Membership](https://www.greenbuttonalliance.org/membership-information)
- [Contact Us](https://www.greenbuttonalliance.org/contact-us)
- [Archive](https://archive.greenbuttondata.org/)

## Mandate and Access Posture

| Question | Finding |
| --- | --- |
| Mandate regime | `green-button-voluntary` — GBA stewards a standard adopted without federal compulsion in the United States |
| Mandate status | `not-applicable` — GBA is a standards body, not an obligated data holder, and runs no live implementation of its own |
| Data standard | Green Button / NAESB REQ.21 ESPI v4.0 (and v3.3), over Atom + OAuth 2.0 |
| Specification freely downloadable | **No** — the normative standard must be purchased from NAESB; only the derived OpenAPI and explanatory pages are free |
| Consumer data API | No — GBA holds no customer data; it publishes the contract others implement |
| Market data open | No — GBA publishes no grid or market data; Directory Services is HTML-only and forbids automated retrieval |
| Access gate | `none-published` — there is no live GBA API to onboard to; the sandbox is out of service until 2026Q3 |
| Auth model | OAuth 2.0 (authorization code + client credentials, RFC 7591/7592 dynamic client registration, TLS 1.3 under ESPI v4.0) for Green Button; separate OpenID Connect for association member SSO |
| Home market | United States |

Full probe log, HTTP statuses and harvest provenance are in [review.yml](review.yml).

## Maintainers

- Kin Lane — kin@apievangelist.com
