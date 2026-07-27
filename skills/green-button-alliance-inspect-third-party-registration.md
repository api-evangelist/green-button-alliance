---
name: Inspect a Green Button Third Party registration
description: Read the ApplicationInformation resource to discover a Data Custodian's OAuth endpoints, supported function-block scopes and notification URI before integrating.
api: openapi/green-button-alliance-green-button-api-openapi.yml
operations: [findApplicationInformations, getApplicationInformation]
generated: '2026-07-27'
method: generated
source: openapi/green-button-alliance-application-information-openapi.yml + openapi/green-button-alliance-green-button-api-openapi.yml
---

# Inspect a Green Button Third Party registration

`ApplicationInformation` is Green Button's discovery document. It is created when a
Third Party registers with a Data Custodian, and it doubles as the RFC 7591 / RFC 7592
dynamic client registration record. Read it **before** writing any integration code:
it tells you that utility's OAuth endpoints, its bulk endpoint template, and — most
importantly — which ESPI **function blocks it actually supports**.

## Steps

1. **List registrations.** Call `findApplicationInformations`
   (`GET /espi/1_1/resource/ApplicationInformation`), paging with `start-index` and
   `max-results`.
2. **Read one.** Call `getApplicationInformation`
   (`GET /espi/1_1/resource/ApplicationInformation/{applicationInformationId}`).
3. **Harvest the endpoints** — do not hardcode them:
   - `authorizationServerAuthorizationEndpoint` — where you send the customer.
   - `authorizationServerTokenEndpoint` — where you exchange the code.
   - `authorizationServerRegistrationEndpoint` — RFC 7591 dynamic registration.
   - `dataCustodianResourceEndpoint` — the base of every `/espi/1_1/resource` call.
   - `dataCustodianBulkRequestURI` — the bulk template, `.../Batch/Bulk/{bulkId}`.
   - `thirdPartyNotifyUri` — where **this utility will POST** the BatchList push
     notification (see `asyncapi/green-button-alliance-webhooks.yml`).
4. **Read `scope[]` as the capability list.** Each entry is a full function-block scope
   string, e.g.
   `FB=1_3_4_5_13_31_37_39;IntervalDuration=900;BlockDuration=monthly;HistoryLength=13`.
   The resource may carry **multiple** `scope` entries; request one of them, not a scope
   you composed yourself. Decode the ids against
   `vocabulary/green-button-alliance-function-blocks.yml`.
5. **Check the statuses before integrating.**
   - `dataCustodianApplicationStatus`: `1` Review, `2` Production (Live), `3` On Hold,
     `4` Revoked.
   - `thirdPartyApplicationStatus`: `1` Development, `2` Review/Test, `3` Production
     (Live), `4` Retired.
   - Anything other than Live on either side means you are not in production.
6. **Note credential expiry.** `client_secret_expires_at` is an epoch timestamp; `0`
   means the secret never expires. `client_id_issued_at` records when it was assigned.

## Rules

- **Ignore the two deprecated fields.** `thirdPartyScopeSelectionURI` and
  `dataCustodianScopeSelectionScreenURI` are marked `[DEPRECATED]` in the published
  spec. Do not build the scope-selection handoff on them.
- **Never log or echo `client_secret` or `registration_access_token`.** Both are
  returned inline on this resource.
- **`getApplicationInformation` is declared in two Green Button documents** — the CMD
  document (item by id) and the SwaggerHub ApplicationInformation document (collection).
  Bind to the CMD document; see `mcp/green-button-alliance-tool-crosswalk.yml`.
- **Treat the values as that utility's truth, not Green Button's.** Every certified Data
  Custodian publishes its own ApplicationInformation with different endpoints and a
  different supported function-block set.
