# Green Button Alliance

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

The Green Button Alliance (GBA) is the non-profit that stewards, tests and certifies the Green Button standard — the NAESB REQ.21 Energy Services Provider Interface (ESPI) profile for utility customer electricity, natural gas and water usage data, in its Download My Data (DMD) and Connect My Data (CMD) forms. Incorporated in North Carolina and headquartered at PO Box 268, Jamison, Pennsylvania, it was formed after the 2012 White House / U.S. Department of Energy / NIST call to action and is the industry's only source of Green Button certification (Data Custodian DMD $3,000, CMD $3,200, membership not required), alongside a free public Directory Services listing of utilities, third-party apps and platform providers. GBA sits in the standards-and-certification layer of the United States energy value chain, above the investor-owned utilities and the energy-data platforms (UtilityAPI, Con Edison and Enbridge Gas are sponsor members) that actually move consumer data. Its API posture is contracts without a service: three real OpenAPI 3.x definitions - the CMD ESPI resource server, the ApplicationInformation registration resource, and the OpenESPI OAuth 2.0 / OIDC authorization server - are published free under Apache 2.0 on GitHub, but the normative ESPI v4.0 standard itself must be purchased from NAESB, GBA operates no production consumer-data or market-data API of its own, and its ESPI sandbox at sandbox.greenbuttonalliance.org:8443 is offline pending a replacement platform expected 2026Q3. Green Button in the United States is voluntary — there is no federal mandate — with obligation arriving only through state action and, outside the US, Ontario's O. Reg. 633/21.

**Areas:** Energy · United States · Utilities · Electricity · Gas · Water · Smart Metering · Green Button · ESPI · Standards Body · Certification · Consumer Energy Data

## Green Button Alliance on APIs.io

Everything profiled for Green Button Alliance is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/green-button-alliance/](https://apis.io/providers/green-button-alliance/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Green Button Third Party (OpenESPI) API](https://apis.io/apis/green-button-alliance/green-button-third-party-api/) — The Third Party side of the OpenESPI reference implementation — ApplicationInformation, Authorization and RetailCustomer operations documented as legacy…
- [Green Button Alliance Application Information API](https://apis.io/apis/green-button-alliance/green-button-alliance-applicationinformation-api/) — The ApplicationInformation API from Green Button Alliance — 2 operation(s) for applicationinformation.
- [Green Button Alliance Authorization API](https://apis.io/apis/green-button-alliance/green-button-alliance-authorization-api/) — Authorization endpoints
- [Green Button Alliance Batch API](https://apis.io/apis/green-button-alliance/green-button-alliance-batch-api/) — Batch data transfer endpoints
- [Green Button Alliance DataCustodian Integration API](https://apis.io/apis/green-button-alliance/green-button-alliance-datacustodian-integration-api/) — Integration with OpenESPI DataCustodian
- [Green Button Alliance OAuth2 Client Management API](https://apis.io/apis/green-button-alliance/green-button-alliance-oauth2-client-management-api/) — Manage OAuth2 client registrations
- [Green Button Alliance OAuth2 Standard API](https://apis.io/apis/green-button-alliance/green-button-alliance-oauth2-standard-api/) — Standard OAuth2 endpoints
- [Green Button Alliance OIDC API](https://apis.io/apis/green-button-alliance/green-button-alliance-oidc-api/) — OpenID Connect endpoints
- [Green Button Alliance Usage Point API](https://apis.io/apis/green-button-alliance/green-button-alliance-usagepoint-api/) — Usage Point endpoints

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Green Button Alliance Webhooks](https://apis.io/asyncapis/green-button-alliance/green-button-alliance-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [green-button-alliance](https://apis.io/servers/green-button-alliance/green-button-alliance/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Green Button Alliance Agentic Access](https://apis.io/agentic-access/green-button-alliance/green-button-alliance-agentic-access/)

#### Examples (4)

Example requests and responses.

- [Green Button Alliance Backchannel Subscription Request](https://apis.io/examples/green-button-alliance/green-button-alliance-backchannel-subscription-request/)
- [Green Button Alliance Backchannel Subscription Response](https://apis.io/examples/green-button-alliance/green-button-alliance-backchannel-subscription-response/)
- [Green Button Alliance Token Response Bulk](https://apis.io/examples/green-button-alliance/green-button-alliance-token-response-bulk/)
- [Green Button Alliance Token Response Subscription](https://apis.io/examples/green-button-alliance/green-button-alliance-token-response-subscription/)

#### Collections (3)

Postman and Open Collection request collections.

- [Green Button Resource Server ApplicationInformation API Documentation](https://apis.io/collections/green-button-alliance/open-green-button-alliance-application-information/)
- [OpenESPI Authorization Server API](https://apis.io/collections/green-button-alliance/open-green-button-alliance-authorization-server/)
- [Green Button API Documentation](https://apis.io/collections/green-button-alliance/open-green-button-alliance-green-button-api/)

#### Overlays (3)

OpenAPI overlays, including conversational phrasing for each operation.

- [Green Button Alliance Application Information Overlay](https://apis.io/overlays/green-button-alliance/green-button-alliance-application-information-overlay/)
- [Green Button Alliance Authorization Server Overlay](https://apis.io/overlays/green-button-alliance/green-button-alliance-authorization-server-overlay/)
- [Green Button Alliance Green Button Api Overlay](https://apis.io/overlays/green-button-alliance/green-button-alliance-green-button-api-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Green Button Alliance Authentication](https://apis.io/security/green-button-alliance/green-button-alliance-authentication/)
- [Green Button Alliance Domain Security](https://apis.io/security/green-button-alliance/green-button-alliance-domain-security/)
- [Green Button Alliance Vulnerability Disclosure](https://apis.io/security/green-button-alliance/green-button-alliance-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Green Button Alliance Scopes](https://apis.io/scopes/green-button-alliance/green-button-alliance-scopes/)

#### Rate limits (1)

Published request limits.

- [Green Button Alliance Rate Limits](https://apis.io/rate-limits/green-button-alliance/green-button-alliance-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.greenbuttonalliance.org/)
- [Documentation](https://www.greenbuttonalliance.org/developer-resources)
- [API reference](https://greenbuttonalliance.github.io/OpenESPI-GreenButton-API-Documentation/API/)
- [Pricing](https://www.greenbuttonalliance.org/offerings/certification)
- [Sign up](https://www.greenbuttonalliance.org/register)
- [Support](https://www.greenbuttonalliance.org/faqs-technical)
- [Blog](https://www.greenbuttonalliance.org/news)
- [Security](https://github.com/GreenButtonAlliance/OpenESPI-GreenButton-Java/blob/main/openespi-common/SECURITY.md)
- [Terms of service](https://www.greenbuttonalliance.org/legal)
- [Privacy policy](https://www.greenbuttonalliance.org/privacy-policy)
- [GitHub](https://github.com/GreenButtonAlliance)

## API Evangelist rating

**Kin Score 50.9** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 56.3 |
| Contract governance | 33.3 |
| Operational transparency | 21.1 |
| Developer ergonomics | 54.2 |
| Access clarity | 44.7 |

**Agent readiness 41.2** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | verified |
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
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 39.3** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/green-button-alliance/](https://apis.io/providers/green-button-alliance/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Green Button Alliance: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/green-button-alliance/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
