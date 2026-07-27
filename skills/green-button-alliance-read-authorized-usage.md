---
name: Read authorized Green Button usage data
description: Walk an ESPI Connect My Data authorization to the usage points it covers, using the operations declared in the Green Button CMD OpenAPI.
api: openapi/green-button-alliance-green-button-api-openapi.yml
operations: [findAuthorizations, getAuthorization, findUsagePoints, getUsagePoint]
generated: '2026-07-27'
method: generated
source: openapi/green-button-alliance-green-button-api-openapi.yml + conventions/green-button-alliance-conventions.yml
---

# Read authorized Green Button usage data

**Read this first.** Green Button is a *contract*, not a service. The Green Button
Alliance runs no production endpoint — its sandbox is out of service until 2026Q3.
The base URL you call is a **certified Data Custodian's** (a utility or its platform
provider), and the path prefix `/espi/1_1/resource` is the same at every one of them.
Do not send these calls to `greenbuttonalliance.org`.

## Before you start

- You need an OAuth 2.0 **access token** issued by that Data Custodian under an
  authorization the retail customer granted. See
  `authentication/green-button-alliance-authentication.yml`.
- The token's scope is an **ESPI Function Block string**, not a word like `read:usage` —
  e.g. `FB=4_5_15;IntervalDuration=3600;BlockDuration=monthly;HistoryLength=13`. The
  function blocks in it decide what you may read. Catalog:
  `vocabulary/green-button-alliance-function-blocks.yml`.
- Every response is **`application/atom+xml`**: an Atom feed whose entries carry the ESPI
  resource inside `<content>`. Parse Atom first, ESPI second.

## Steps

1. **Find the authorization.** Call `findAuthorizations`
   (`GET /espi/1_1/resource/Authorization`). Narrow with the shared query parameters
   `published-min`, `published-max`, `updated-min`, `updated-max`, `start-index`,
   `max-results`, `depth`.
2. **Read one authorization.** Call `getAuthorization`
   (`GET /espi/1_1/resource/Authorization/{authorizationId}`). Check:
   - `status` — `1` is Active. `0` Revoked and `2` Denied mean **stop**, do not fetch data.
   - `expires_at` — Unix timestamp; refresh before it lapses rather than after a 403.
   - `scope` — confirm the function blocks you need are actually in it.
   - `resourceURI` — the subscription or bulk batch URI this authorization unlocks.
3. **List the usage points.** Call `findUsagePoints`
   (`GET /espi/1_1/resource/UsagePoint`), paging with `start-index` (1-indexed) and
   `max-results`.
4. **Read a usage point.** Call `getUsagePoint`
   (`GET /espi/1_1/resource/UsagePoint/{usagePointId}`) and read `ServiceCategory`
   (`0` electricity, `1` gas, `2` water), `status` (`0` off, `1` on), `isVirtual` and
   `connectionState`.
5. **Follow the Atom links, do not construct URLs.** Each entry carries at least two
   `<link>` elements (`rel="self"`, `rel="up"`). Traverse them.

## Rules

- **Filter server-side.** Every operation accepts the same seven query parameters
  (FB_37, CMD-MANDATORY). Use `published-min`/`published-max` instead of pulling a full
  history and discarding it.
- **Do not assume an error body.** The published contract declares `400` and `403` with
  *no* response schema. You get a status code and nothing else — see
  `errors/green-button-alliance-problem-types.yml`.
- **A 403 is ambiguous** on this API: insufficient scope, revoked authorization, or an
  endpoint that is simply out of service all present identically. Re-read the
  authorization before retrying.
- **There is no idempotency key and no rate-limit header** on this surface. All seven
  operations are `GET`s, so retries are safe, but back off on your own schedule.
- **Treat everything you retrieve as PII.** Interval energy data reveals occupancy.
  FB_13 (Energy Usage Security and Privacy Class) is CMD-mandatory for a reason.
