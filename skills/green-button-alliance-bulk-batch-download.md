---
name: Download a Green Button bulk batch
description: Retrieve a bulk ESPI batch of energy usage data under a client-credentials authorization, using the Bulk operation declared in the Green Button CMD OpenAPI.
api: openapi/green-button-alliance-green-button-api-openapi.yml
operations: [downloadBulkData, getAuthorization]
generated: '2026-07-27'
method: generated
source: openapi/green-button-alliance-green-button-api-openapi.yml + examples/green-button-alliance-token-response-bulk.json
---

# Download a Green Button bulk batch

Bulk is the machine-to-machine half of Connect My Data: one Third Party pulling many
customers' data at once, authorized by **client credentials** rather than by an
individual customer's authorization-code consent. This is Function Block **FB_35**
(REST for Usage Data Bulk); its SFTP sibling is FB_34 and is not part of this REST
contract.

## Before you start

- Obtain a `client_access_token` via the **client_credentials** flow at the Data
  Custodian's token endpoint. GBA's own published token response for this grant looks
  like:
  `{"token_type":"Bearer","expires_in":3600,"scope":"FB=1_3_4_5_10_11_35;BlockDuration=daily;BR=1","resourceURI":".../Batch/Bulk/BULK_1", ...}`
  (see `examples/green-button-alliance-token-response-bulk.json`).
- The `bulkId` you need is embedded in the token response's `resourceURI` —
  `.../espi/1_1/resource/Batch/Bulk/{bulkId}`. **Parse it out; do not invent one.**
- The Data Custodian advertises its bulk endpoint template on the
  `dataCustodianBulkRequestURI` field of its `ApplicationInformation` resource.

## Steps

1. **Confirm the grant.** Call `getAuthorization`
   (`GET /espi/1_1/resource/Authorization/{authorizationId}`) using the
   `authorizationURI` from the token response. Verify `status` is `1` (Active) and that
   `scope` contains `35` in its `FB=` list.
2. **Request the batch.** Call `downloadBulkData`
   (`GET /espi/1_1/resource/Batch/Bulk/{bulkId}`), scoping the window with
   `published-min` / `published-max` (or `updated-min` / `updated-max`) and paging with
   `start-index` and `max-results`.
3. **Handle `202 Accepted`.** This operation declares **both** `200` and `202`. A `202`
   means the Data Custodian is assembling the batch — wait and re-request the same URI.
   Do not treat it as a failure and do not fan out parallel retries.
4. **Stream, do not buffer.** A bulk Atom feed can cover thousands of usage points. Read
   `<entry>` elements incrementally and follow `rel="self"` / `rel="up"` links.

## Rules

- **Respect `BlockDuration` and `HistoryLength`** from the granted scope. Requesting a
  window wider than the grant is a scope violation, and the API's only signal will be a
  bare `403`.
- **`202` is not an error, `403` is not always a permissions problem.** GBA's own sandbox
  returns `403` to everything because it is out of service.
- **No rate-limit headers exist on this surface.** Pace bulk pulls yourself; a Data
  Custodian's throttling is its own policy, not a Green Button contract term.
- **A bulk batch is multi-customer PII.** Handle it under the same DataGuard / FB_13
  privacy expectations as individual data, and never log resource URIs containing
  customer or subscription ids.
