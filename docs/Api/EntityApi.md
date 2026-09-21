# Omnismith\Sdk\EntityApi

Entity

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**aggregateEntities()**](EntityApi.md#aggregateEntities) | **POST** /entities/aggregate/{template_id} | Count, sum, average, min or max entities, optionally grouped by attributes |
| [**batchExecuteEntityAction()**](EntityApi.md#batchExecuteEntityAction) | **POST** /entities/batch/actions/{slug} | Execute an action on a selection of entities |
| [**batchWriteEntities()**](EntityApi.md#batchWriteEntities) | **POST** /entities/batch | Apply a batch of mixed entity creates, updates, replaces, and deletes |
| [**createEntity()**](EntityApi.md#createEntity) | **POST** /entities/template/{template} | Create a new dynamic entity |
| [**deleteEntity()**](EntityApi.md#deleteEntity) | **DELETE** /entities/{id} | Soft-delete an entity record |
| [**executeEntityAction()**](EntityApi.md#executeEntityAction) | **POST** /entities/{id}/actions/{slug} | Execute an action on an entity |
| [**exportEntities()**](EntityApi.md#exportEntities) | **POST** /entities/export/{template_id} | Export entities to structured CSV file |
| [**getEntity()**](EntityApi.md#getEntity) | **GET** /entities/{id} | Get an entity record by ID |
| [**getEntityChart()**](EntityApi.md#getEntityChart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory()**](EntityApi.md#getEntityHistory) | **GET** /entities/{id}/history | Get entity dimension change history |
| [**importEntities()**](EntityApi.md#importEntities) | **POST** /entities/import/{template_id} | Import entities from structured CSV file |
| [**ingestEntityMetrics()**](EntityApi.md#ingestEntityMetrics) | **POST** /entities/{id}/metrics | Ingest high-frequency metric observations for an entity |
| [**listEntityActions()**](EntityApi.md#listEntityActions) | **GET** /entities/{id}/actions | List the actions available on an entity |
| [**replaceEntity()**](EntityApi.md#replaceEntity) | **PUT** /entities/{id} | Replace all non-metric attributes of an entity |
| [**searchEntities()**](EntityApi.md#searchEntities) | **POST** /entities/search/{template_id} | Search entities with filtering, sorting, and pagination |
| [**semanticSearchEntities()**](EntityApi.md#semanticSearchEntities) | **POST** /entities/semantic-search | Perform semantic vector similarity search on entities |
| [**updateEntity()**](EntityApi.md#updateEntity) | **PATCH** /entities/{id} | Update entity attribute values |


## `aggregateEntities()`

```php
aggregateEntities($templateId, $aggregateEntitiesRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\AggregateEntities200Response
```

Count, sum, average, min or max entities, optionally grouped by attributes

Answers \"how many\", \"how much\" and \"broken down by\" questions in one call, computed by the database. Use it instead of paginating `searchEntities` and tallying rows: a count or a per-status breakdown of a 10,000-record template is one small response.  ### Filters (`filter_groups`) A list of groups; clauses inside a group are AND-ed, groups are OR-ed. `[[a, b]]` is `a AND b`; `[[a], [b, c]]` is `a OR (b AND c)`; `[]` applies no filter. ```json [   [     {\"field\": \"status\", \"operator\": \"in\", \"value\": [\"018b…0020\", \"018b…0021\"]},     {\"field\": \"created_at\", \"operator\": \"between\", \"value\": [\"2026-01-01\", \"2026-03-31\"]},     {\"field\": \"customer.tier\", \"operator\": \"eq\", \"value\": \"018b…0042\"}   ],   [{\"field\": \"priority\", \"operator\": \"eq\", \"value\": \"018b…0007\"}] ] ``` - **`field`**: attribute slug or UUID, a standard field (`id`, `created_at`, `updated_at`), or a one-hop path `<reference>.<attribute>` that filters on an attribute of the referenced record (e.g. `customer.tier`). One hop only. - **`operator`** and **`value`**: `eq`, `neq`, `gt`, `lt`, `like` (case-insensitive substring), `not-like` take a string; `in`, `not-in` take a non-empty list of strings; `between` takes `[lower, upper]` (inclusive; number, date, datetime attributes and `created_at` / `updated_at`); `empty`, `not-empty` take no value. - List and reference attributes compare the stored id (from `list_item_ids` / `reference_entity_ids` or the schema), never the label. - Unknown fields, operators that do not fit the field, malformed values and paths that do not traverse a reference are refused with 400 naming the valid fields; a path into a template the caller may not view is 403.  ### Grouping `group_by` takes up to 3 attribute slugs or UUIDs. Lists, references, strings, numbers, booleans and dates can be keys. Each group's `key` mirrors `group_by` in order: `value` is the stored value (a list item id, an entity id, a scalar) and `custom_value` is the list item label or the referenced record's display value. A `null` value groups the records that have no value for that attribute. With no `group_by` the whole filtered set is one group.  ### Aggregations `aggregations` takes 1 to 10 `{op, field}` entries and each group's `aggregates` mirrors them in order. - `count` — number of matching records. Takes no field; to count records that have a value, filter with `not-empty`. - `sum`, `avg` — a number attribute. - `min`, `max` — a number, date or datetime attribute.  Numbers come back as floats, dates as RFC 3339 strings, and `null` when no record in the group has a value. Metric attributes are rejected with a 400: they are time series and are reduced over a time window with `getEntityChart`; this endpoint reduces the current dimension values of records.  ### Ordering and limits Groups are ordered by the first aggregation descending (nulls last), then by key, so `[{\"op\": \"count\"}]` first gives a top-N breakdown. `limit` (1-100, default 50) caps the groups returned; `truncated: true` means more groups exist — narrow with `filter_groups` or group by fewer fields.  ### Example ```json {\"filter_groups\": [[{\"field\": \"status\", \"operator\": \"eq\", \"value\": \"018b…0020\"}]],  \"group_by\": [\"tier\"],  \"aggregations\": [{\"op\": \"count\"}, {\"op\": \"sum\", \"field\": \"mrr\"}]} ``` returns ```json {\"data\": [{\"key\": [{\"field\": \"tier\", \"value\": \"018b…0031\", \"custom_value\": \"Team\"}],            \"aggregates\": [{\"op\": \"count\", \"field\": null, \"value\": 12}, {\"op\": \"sum\", \"field\": \"mrr\", \"value\": 3400.5}]}],  \"limit\": 50, \"truncated\": false} ```  Read-only. Applies the caller's template access and row scopes exactly as search does; restricted attributes are not valid fields.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = tenant_user; // string | Template UUID or human-readable template slug
$aggregateEntitiesRequest = new \Omnismith\Sdk\Model\AggregateEntitiesRequest(); // \Omnismith\Sdk\Model\AggregateEntitiesRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->aggregateEntities($templateId, $aggregateEntitiesRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->aggregateEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Template UUID or human-readable template slug | |
| **aggregateEntitiesRequest** | [**\Omnismith\Sdk\Model\AggregateEntitiesRequest**](../Model/AggregateEntitiesRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\AggregateEntities200Response**](../Model/AggregateEntities200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `batchExecuteEntityAction()`

```php
batchExecuteEntityAction($slug, $batchExecuteEntityActionRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\BatchExecuteEntityActionResponse
```

Execute an action on a selection of entities

Runs one named action on many records in a single call — \"confirm these forty\". Each record goes through exactly what `POST /entities/{id}/actions/{slug}` (`execute_entity_action`) does: precondition, field matching, presets, type validation and the template's rules, with history attributed to the action. `values` are the same for every record.  The action is resolved per record on its template, so the selection may span templates that each define the slug; a record whose template does not is reported as `failed` with a 404 body.  At most 100 records per call; page a larger selection.  ### Outcomes By default (`atomic: false`) every record is attempted and the response is `200` with one outcome per record — `executed` with a receipt, or `precondition_failed` / `rule_violated` / `failed` with the error body the single-record endpoint would have returned. Read the counters, then `results` for the records that did not run.  With `atomic: true` the batch runs in one transaction and the first record that does not execute rolls all of it back. That case answers with that record's own error status and body plus `failed_entity_id`, not with a results list.  ### Quotas The dimension-update quota is checked for the whole selection before any record is written.  ### Errors - `400` — the body is not the documented shape, or lists an entity twice. - `402` — the selection would cross the tier's update quota. - `422` — a submitted value does not fit the action (only when nothing could run).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$slug = confirm_attendance; // string | Action slug, as listed by `GET /templates/{templateId}/actions` or `GET /entities/{id}/actions`
$batchExecuteEntityActionRequest = new \Omnismith\Sdk\Model\BatchExecuteEntityActionRequest(); // \Omnismith\Sdk\Model\BatchExecuteEntityActionRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->batchExecuteEntityAction($slug, $batchExecuteEntityActionRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->batchExecuteEntityAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **slug** | **string**| Action slug, as listed by &#x60;GET /templates/{templateId}/actions&#x60; or &#x60;GET /entities/{id}/actions&#x60; | |
| **batchExecuteEntityActionRequest** | [**\Omnismith\Sdk\Model\BatchExecuteEntityActionRequest**](../Model/BatchExecuteEntityActionRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\BatchExecuteEntityActionResponse**](../Model/BatchExecuteEntityActionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `batchWriteEntities()`

```php
batchWriteEntities($batchWriteEntitiesRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\BatchWriteEntitiesResponse
```

Apply a batch of mixed entity creates, updates, replaces, and deletes

Applies an ordered, heterogeneous list of entity writes in a single call: update these twenty, create three, replace two, delete one.  This is distinct from CSV import, which moves a homogeneous set of new rows. Use this endpoint when the set of edits is already computed and addresses known records.  ### Operations Every entry names an `op` and carries exactly the fields for it — nothing more, nothing less: - `create`  — `{ \"op\": \"create\", \"template\": \"<slug|uuid>\", \"id\"?: \"<uuidv7>\", \"attributes\": { ... } }` (`attributes` may be `{}`) - `update`  — `{ \"op\": \"update\", \"id\": \"<uuid>\", \"attributes\": { ... } }` (non-empty; partial, like PATCH) - `replace` — `{ \"op\": \"replace\", \"id\": \"<uuid>\", \"attributes\": { ... } }` (like PUT: **attributes absent from the map are cleared**; `{}` clears all; metrics rejected) - `delete`  — `{ \"op\": \"delete\", \"id\": \"<uuid>\" }` (soft delete)  `id` always means the entity id; `template` always means the template slug or UUID.  ### `attributes` An object keyed by attribute **slug or UUID** — mix them freely. Each value is a plain scalar, a backfill object `{ \"value\": ..., \"updated_at\": \"<RFC 3339>\" }`, or an operation object `{ \"op\": \"increment\", \"value\": <number> }`:  ```json {   \"hostname\": \"edge-fra-01\",   \"cpu_cores\": 8,   \"is_active\": true,   \"notes\": null,   \"01a094f1-24be-7154-a5bd-3b5c33c930fb\": \"01a094f1-4c1d-7498-b73b-48ae46da900b\",   \"operational_status\": { \"value\": \"Active\", \"updated_at\": \"2026-09-12T12:23:52Z\" },   \"restart_count\": { \"op\": \"increment\", \"value\": 1 } } ```  `null` clears an attribute. `{ \"op\": \"increment\", \"value\": n }` adds `n` to the stored number without you reading it first (number attributes and metrics only; concurrent increments never lose an update). Every attribute must belong to the entity's template and may appear only once (the same attribute as slug *and* UUID is rejected). Full value rules are on the `EntityAttributesInput` schema.  At most 100 operations per call. Larger sets must be split.  ### Failure handling By default (`atomic: false`) every operation is attempted, successes stand, and each failure is reported against its index with the same error body the single-entity endpoint would have returned. The response is `200` regardless of how many entries failed; read `failed` and the per-item `status`.  With `atomic: true` the whole batch runs in one transaction and the first failure rolls all of it back. That case answers with the failing operation's own error status and body plus `failed_index`, not with a results list. Atomic batches reject metric attribute values, because metric telemetry is published outside the transaction and cannot be rolled back.  ### Quotas Tier quotas are evaluated for the whole batch before any of it is applied, so a batch that would cross the limit is refused as a unit rather than applied halfway.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$batchWriteEntitiesRequest = new \Omnismith\Sdk\Model\BatchWriteEntitiesRequest(); // \Omnismith\Sdk\Model\BatchWriteEntitiesRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->batchWriteEntities($batchWriteEntitiesRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->batchWriteEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batchWriteEntitiesRequest** | [**\Omnismith\Sdk\Model\BatchWriteEntitiesRequest**](../Model/BatchWriteEntitiesRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\BatchWriteEntitiesResponse**](../Model/BatchWriteEntitiesResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createEntity()`

```php
createEntity($template, $xOmnismithProjectId, $createEntityRequest): \Omnismith\Sdk\Model\CreateEntity201Response
```

Create a new dynamic entity

Creates one entity of the template named in the path — `{template}` is the template's slug or UUID — and returns its id. Pass `id` to choose the entity's UUIDv7 yourself (cross-system keys); otherwise one is generated. An `id` that already exists — even a soft-deleted entity's — is rejected with `409` rather than overwritten: if a retry might be hitting this because an earlier call's response was lost, `GET /entities/{id}` first to check whether it already carries what you meant to write, rather than retrying blindly.  ### `attributes` An object keyed by attribute **slug or UUID** — mix them freely. Each value is a plain scalar, a backfill object `{ \"value\": ..., \"updated_at\": \"<RFC 3339>\" }`, or an operation object `{ \"op\": \"increment\", \"value\": <number> }`:  ```json {   \"hostname\": \"edge-fra-01\",   \"cpu_cores\": 8,   \"is_active\": true,   \"notes\": null,   \"01a094f1-24be-7154-a5bd-3b5c33c930fb\": \"01a094f1-4c1d-7498-b73b-48ae46da900b\",   \"operational_status\": { \"value\": \"Active\", \"updated_at\": \"2026-09-12T12:23:52Z\" },   \"restart_count\": { \"op\": \"increment\", \"value\": 1 } } ```  `null` clears an attribute. `{ \"op\": \"increment\", \"value\": n }` adds `n` to the stored number without you reading it first (number attributes and metrics only; concurrent increments never lose an update). Every attribute must belong to the entity's template and may appear only once (the same attribute as slug *and* UUID is rejected). Full value rules are on the `EntityAttributesInput` schema.  `attributes` is required; send `{}` to create an entity with no values yet. Metric attributes in the map are appended to the entity's time series; everything else becomes the entity's initial state and is recorded in its history. Operation objects (`{ \"op\": ... }`) are rejected on create: there is no stored value to operate on yet, so send the initial number as a literal.  ### Errors - `400` — the body is not the documented shape (missing `attributes`, a list instead of an object, unknown fields, wrong types). - `422` — the shape is right but the content is not: unknown attribute, attribute not on the template, duplicate attribute, bad `updated_at`, a value that fails its attribute type, or an operation on an attribute that is not a number. `errors` names the exact field, e.g. `attributes.status`. - `404` — no template with that slug or UUID in this project. - `409` — the given `id` already exists.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template = article; // string | Template UUID or human-readable slug
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$createEntityRequest = new \Omnismith\Sdk\Model\CreateEntityRequest(); // \Omnismith\Sdk\Model\CreateEntityRequest

try {
    $result = $apiInstance->createEntity($template, $xOmnismithProjectId, $createEntityRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->createEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template** | **string**| Template UUID or human-readable slug | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **createEntityRequest** | [**\Omnismith\Sdk\Model\CreateEntityRequest**](../Model/CreateEntityRequest.md)|  | [optional] |

### Return type

[**\Omnismith\Sdk\Model\CreateEntity201Response**](../Model/CreateEntity201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteEntity()`

```php
deleteEntity($id, $xOmnismithProjectId)
```

Soft-delete an entity record

Marks an entity record as soft-deleted by setting its `deleted_at` timestamp.  Soft-deleted entities are immediately excluded from standard entity searches, BI row queries, and direct retrieval endpoints. Associated historical change logs and time-series telemetry remain preserved for audit compliance.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID) to soft-delete
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->deleteEntity($id, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->deleteEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) to soft-delete | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `executeEntityAction()`

```php
executeEntityAction($id, $slug, $xOmnismithProjectId, $executeEntityActionRequest): \Omnismith\Sdk\Model\ExecuteEntityActionResponse
```

Execute an action on an entity

Runs one named action on one record as a single atomic write. Prefer this over a plain update (`PATCH /entities/{id}`, the `update_entity` tool) whenever `GET /entities/{id}/actions` (`list_entity_actions`) lists an action for what you intend: the action's presets are applied for you and its required fields are enforced.  ### What happens 1. The action's precondition is checked against the record's current values — `409` if it does not hold, with the reason. 2. `values` are matched to the action's `fields`; an attribute the action does not ask for, or an empty required field, is `422` keyed by `attributes.<slug>`. 3. Presets are merged on top of `values` (presets win) and the result is written exactly like an entity update: attribute types are validated and the template's rules are enforced (`422` on a violation, in the same `attributes.<slug>` shape).  The response is a receipt naming what was written — for a number field sent as `{ \"op\": \"increment\", \"value\": n }` that is the operation itself; the resolved number lands in the record and its history. History rows produced by the write carry the action's slug.  ### Errors - `400` — the body is not the documented shape. - `403` — the caller may not edit this record. - `404` — no such entity, or the template has no enabled action with this slug. - `409` — the precondition does not hold; `detail` says which attribute and why. - `422` — a required field is empty, a value fails its attribute type, or a rule refuses the write.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$slug = confirm_attendance; // string | Action slug, as listed by `GET /entities/{id}/actions`
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$executeEntityActionRequest = new \Omnismith\Sdk\Model\ExecuteEntityActionRequest(); // \Omnismith\Sdk\Model\ExecuteEntityActionRequest

try {
    $result = $apiInstance->executeEntityAction($id, $slug, $xOmnismithProjectId, $executeEntityActionRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->executeEntityAction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **slug** | **string**| Action slug, as listed by &#x60;GET /entities/{id}/actions&#x60; | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **executeEntityActionRequest** | [**\Omnismith\Sdk\Model\ExecuteEntityActionRequest**](../Model/ExecuteEntityActionRequest.md)|  | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ExecuteEntityActionResponse**](../Model/ExecuteEntityActionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `exportEntities()`

```php
exportEntities($templateId, $exportEntitiesRequest, $xOmnismithProjectId, $sortField, $sortDirection): \SplFileObject
```

Export entities to structured CSV file

Exports entity records of a template schema matching filter criteria as a streaming CSV download.  ### Re-importable CSV Schema Format The generated CSV conforms to the Omnismith two-row metadata specification, making it directly compatible with `POST /entities/import/{template_id}`: - **Row 1**: Display column names and attribute aliases. - **Row 2**: Metadata row prefixed with `#` containing attribute UUIDs and column IDs (e.g. `#id`, `#018b2f1b-8c1a...`). - **Row 3+**: Entity data records.  Accepts the same `filter_groups` and `global_search` payload as `searchEntities`.  ### Filters (`filter_groups`) A list of groups; clauses inside a group are AND-ed, groups are OR-ed. `[[a, b]]` is `a AND b`; `[[a], [b, c]]` is `a OR (b AND c)`; `[]` applies no filter. ```json [   [     {\"field\": \"status\", \"operator\": \"in\", \"value\": [\"018b…0020\", \"018b…0021\"]},     {\"field\": \"created_at\", \"operator\": \"between\", \"value\": [\"2026-01-01\", \"2026-03-31\"]},     {\"field\": \"customer.tier\", \"operator\": \"eq\", \"value\": \"018b…0042\"}   ],   [{\"field\": \"priority\", \"operator\": \"eq\", \"value\": \"018b…0007\"}] ] ``` - **`field`**: attribute slug or UUID, a standard field (`id`, `created_at`, `updated_at`), or a one-hop path `<reference>.<attribute>` that filters on an attribute of the referenced record (e.g. `customer.tier`). One hop only. - **`operator`** and **`value`**: `eq`, `neq`, `gt`, `lt`, `like` (case-insensitive substring), `not-like` take a string; `in`, `not-in` take a non-empty list of strings; `between` takes `[lower, upper]` (inclusive; number, date, datetime attributes and `created_at` / `updated_at`); `empty`, `not-empty` take no value. - List and reference attributes compare the stored id (from `list_item_ids` / `reference_entity_ids` or the schema), never the label. - Unknown fields, operators that do not fit the field, malformed values and paths that do not traverse a reference are refused with 400 naming the valid fields; a path into a template the caller may not view is 403.  ### Sorting Sort results via `sort_field` (attribute UUID, slug, or standard timestamp) and `sort_direction` (`asc`/`desc`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010001; // string | Unique identifier (UUID) of the template schema to export
$exportEntitiesRequest = new \Omnismith\Sdk\Model\ExportEntitiesRequest(); // \Omnismith\Sdk\Model\ExportEntitiesRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$sortField = created_at; // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by
$sortDirection = asc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)

try {
    $result = $apiInstance->exportEntities($templateId, $exportEntitiesRequest, $xOmnismithProjectId, $sortField, $sortDirection);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->exportEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Unique identifier (UUID) of the template schema to export | |
| **exportEntitiesRequest** | [**\Omnismith\Sdk\Model\ExportEntitiesRequest**](../Model/ExportEntitiesRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **sortField** | **string**| Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [optional] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;asc&#39;] |

### Return type

**\SplFileObject**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `text/csv`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntity()`

```php
getEntity($id, $xOmnismithProjectId, $verbose, $fields): \Omnismith\Sdk\Model\EntityResponse
```

Get an entity record by ID

Retrieves the full hydrated record for a dynamic entity by its unique identifier (UUID).  ### Attribute Values Shape (`verbose`) By default `attribute_values` is a compact object mapping each attribute slug to its display value (e.g. `{\"title\": \"Fix login\", \"status\": \"Open\", \"assignee\": \"Jane Doe\"}`). Attributes without a slug are keyed by their UUID; attributes whose value is empty are omitted. List, reference and file attributes show their label; the ids behind those labels come alongside in `list_item_ids`, `reference_entity_ids` and `file_ids` (same keys) — use those ids for writes and filters, which take ids rather than labels. Pass `verbose=true` to receive an array of `EntityAttributeValue` items instead, each carrying the attribute `id`, `slug`, raw `value`, resolved display label (`custom_value`) and `reference_entity_id`; the id maps are then omitted.  ### Selective Field Projection (`fields`) By default, all dynamic attributes defined on the entity's template are hydrated and returned. To optimize performance and minimize response payload volume, supply the `fields` query parameter as a comma-separated list of attribute slugs, attribute UUIDs, or root fields (e.g. `?fields=title,status`). - **Selective Hydration**: Non-requested attribute values are excluded from database queries and omitted from `attribute_values`. - **Root Metadata Guaranteed**: Essential entity identifiers and timestamps (`id`, `template_id`, `template_slug`, `created_at`, `updated_at`) are always returned regardless of the projection. - **Strict Validation**: Requesting unknown field names returns HTTP 400 Bad Request naming all valid attribute slugs and standard fields for the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$verbose = false; // bool | When true, attribute_values is an array of EntityAttributeValue items with attribute id, slug, raw value, resolved custom_value and reference_entity_id. When false (default), attribute_values is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in list_item_ids, reference_entity_ids and file_ids.
$fields = ["title","status"]; // string[] | Comma-separated list of attribute slugs, attribute UUIDs, or root fields to project (e.g. \"title,status\"). When specified, only the requested attributes are fetched and returned in attribute_values, avoiding database hydration for unneeded attributes and significantly reducing response payload size. If omitted, all attributes defined on the template are returned.

try {
    $result = $apiInstance->getEntity($id, $xOmnismithProjectId, $verbose, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **verbose** | **bool**| When true, attribute_values is an array of EntityAttributeValue items with attribute id, slug, raw value, resolved custom_value and reference_entity_id. When false (default), attribute_values is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in list_item_ids, reference_entity_ids and file_ids. | [optional] [default to false] |
| **fields** | [**string[]**](../Model/string.md)| Comma-separated list of attribute slugs, attribute UUIDs, or root fields to project (e.g. \&quot;title,status\&quot;). When specified, only the requested attributes are fetched and returned in attribute_values, avoiding database hydration for unneeded attributes and significantly reducing response payload size. If omitted, all attributes defined on the template are returned. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\EntityResponse**](../Model/EntityResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntityChart()`

```php
getEntityChart($id, $attributeIds, $start, $end, $xOmnismithProjectId, $aggregateFunc, $bucketWidth): \Omnismith\Sdk\Model\GetEntityChart200Response
```

Get entity chart time-series data

Retrieves aggregated, time-bucketed metric time-series data for an entity.  ### Metric Attribute Filtering (`attribute_ids`) Pass one or more comma-separated metric attribute UUIDs to aggregate across the query window.  ### Aggregation Functions (`aggregate_func`) Supported aggregation operations within each bucket: - `avg` (default): Arithmetic mean of values - `sum`: Sum total of values - `min` / `max`: Minimum / Maximum observed value - `count`: Number of recorded observations - `first` / `last`: Earliest / Latest observation within the time bucket  ### Time Intervals & Bucket Widths (`bucket_width`) Values follow standard time interval notation: `1 second`, `5 seconds`, `10 seconds`, `1 minute` (1m), `5 minutes` (5m), `10 minutes`, `15 minutes`, `30 minutes`, `1 hour` (1h), `6 hours`, `12 hours`, `1 day` (1d), `1 week`, `1 month`.  ### Query Window (`start` & `end`) Query range is defined by `start` and `end` timestamps supplied as integer Unix epoch seconds.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$attributeIds = 018b2f1b-8c1a-75b3-8000-7f0000010010,018b2f1b-8c1a-75b3-8000-7f0000010011; // string | Comma-separated metric attribute UUIDs to aggregate
$start = 1774396800; // int | Start timestamp as Unix epoch in seconds
$end = 1774483200; // int | End timestamp as Unix epoch in seconds
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$aggregateFunc = avg; // string | Aggregation function applied within each bucket
$bucketWidth = 1 hour; // string | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day)

try {
    $result = $apiInstance->getEntityChart($id, $attributeIds, $start, $end, $xOmnismithProjectId, $aggregateFunc, $bucketWidth);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntityChart: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **attributeIds** | **string**| Comma-separated metric attribute UUIDs to aggregate | |
| **start** | **int**| Start timestamp as Unix epoch in seconds | |
| **end** | **int**| End timestamp as Unix epoch in seconds | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **aggregateFunc** | **string**| Aggregation function applied within each bucket | [optional] [default to &#39;avg&#39;] |
| **bucketWidth** | **string**| Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) | [optional] [default to &#39;1 hour&#39;] |

### Return type

[**\Omnismith\Sdk\Model\GetEntityChart200Response**](../Model/GetEntityChart200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntityHistory()`

```php
getEntityHistory($id, $xOmnismithProjectId, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail): \Omnismith\Sdk\Model\GetEntityHistory200Response
```

Get entity dimension change history

Retrieves the immutable change audit log for an entity's dimension attribute mutations.  ### Dedicated Dimension Audit Log Records all historical mutations to dimension, list, and reference attribute values. High-volume metric telemetry observations bypass this log and are stored in dedicated time-series storage, keeping the audit log clean and performant.  ### Filtering & Search - `attribute_ids`: Filter by one or more comma-separated attribute UUIDs. - `search`: Text search matching historical serialized values. - `start` and `end`: Filter history records within a timestamp window (ISO 8601 or `YYYY-MM-DD HH:MM:SS`). - `author_email`: Filter by the actor who performed the mutation.  ### Pagination & Sorting Supports 1-indexed pagination (`page`, `limit` up to 100) and sorting by `created_at`, `attribute_id`, or `value` (`asc`/`desc`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$page = 1; // int | 1-based page number for pagination
$limit = 20; // int | Number of history records per page (1-100)
$sortBy = created_at; // string | Field to sort change logs by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)
$search = Electronics; // string | Free-text search filter matching against old and new attribute values
$attributeIds = 018b2f1b-8c1a-75b3-8000-7f0000010002,018b2f1b-8c1a-75b3-8000-7f0000010003; // string | Comma-separated attribute UUIDs to filter change history
$start = 2026-08-01T00:00:00Z; // \DateTime | Filter change records occurring on or after this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format)
$end = 2026-08-26T23:59:59Z; // \DateTime | Filter change records occurring on or before this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format)
$authorEmail = demo@omnismith.io; // string | Filter change records by author or actor email

try {
    $result = $apiInstance->getEntityHistory($id, $xOmnismithProjectId, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntityHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **page** | **int**| 1-based page number for pagination | [optional] [default to 1] |
| **limit** | **int**| Number of history records per page (1-100) | [optional] [default to 20] |
| **sortBy** | **string**| Field to sort change logs by | [optional] [default to &#39;created_at&#39;] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;desc&#39;] |
| **search** | **string**| Free-text search filter matching against old and new attribute values | [optional] |
| **attributeIds** | **string**| Comma-separated attribute UUIDs to filter change history | [optional] |
| **start** | **\DateTime**| Filter change records occurring on or after this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) | [optional] |
| **end** | **\DateTime**| Filter change records occurring on or before this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) | [optional] |
| **authorEmail** | **string**| Filter change records by author or actor email | [optional] |

### Return type

[**\Omnismith\Sdk\Model\GetEntityHistory200Response**](../Model/GetEntityHistory200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `importEntities()`

```php
importEntities($templateId, $file, $xOmnismithProjectId): \Omnismith\Sdk\Model\ImportEntities200Response
```

Import entities from structured CSV file

Bulk imports entity records into a template schema from a structured CSV file.  ### Upsert Semantics - **Update existing**: If a data row includes an `id` matching an existing entity UUID, that entity is updated. - **Create new**: If the `id` column is empty, omitted, or contains a new UUID, a new entity record is created.  ### Required 2-Row CSV Header Format The CSV file must follow the Omnismith two-row header format (identical to the output of `POST /entities/export/{template_id}`): - **Row 1 (Display Header)**: Human-readable attribute names or aliases (e.g. `ID`, `SKU`, `Price`, `Category`). - **Row 2 (Metadata Marker)**: Canonical attribute identifiers prefixed by `#` (e.g. `#id`, `#018b2f1b-8c1a...`, `#018b2f1b-8c1b...`). - **Row 3+ (Data Rows)**: Serialized entity values conforming to the template's attribute data types.  ### Attribute Value Validation - List attributes require valid `ListItem` option UUIDs. - Reference attributes require existing target `Entity` UUIDs. - Number/Date/Boolean fields must match required format syntax.  ### Execution Summary Returns an execution report detailing counts of created, updated, skipped, and failed rows, along with granular row/column error messages.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010001; // string | Unique identifier (UUID) of the template schema to import entities into
$file = '/path/to/file.txt'; // \SplFileObject | CSV file exported from the export endpoint or matching its format
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->importEntities($templateId, $file, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->importEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Unique identifier (UUID) of the template schema to import entities into | |
| **file** | **\SplFileObject****\SplFileObject**| CSV file exported from the export endpoint or matching its format | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ImportEntities200Response**](../Model/ImportEntities200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `ingestEntityMetrics()`

```php
ingestEntityMetrics($id, $ingestMetricsRequest, $xOmnismithProjectId)
```

Ingest high-frequency metric observations for an entity

Ingests time-series metric observations for an entity record.  ### Batch Telemetry Ingestion Accepts a batch array of metric observations (`metric_values`). Each observation targets a metric attribute by `attribute_id` (UUID) or `attribute_slug` and specifies a numeric `value`.  ### High-Throughput Streaming Architecture Metric ingestion calls stream directly into the high-throughput telemetry ingestion pipeline. Asynchronous background consumers persist data points into tenant-scoped time-series storage configured with automated retention and continuous aggregation rollups.  ### Strict Metric Attribute Constraint Only attributes defined with `attribute_type: Metric` are accepted by this endpoint. Mutations to dimension, list, or reference attributes must use `PATCH /entities/{id}` instead.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$ingestMetricsRequest = new \Omnismith\Sdk\Model\IngestMetricsRequest(); // \Omnismith\Sdk\Model\IngestMetricsRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->ingestEntityMetrics($id, $ingestMetricsRequest, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->ingestEntityMetrics: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **ingestMetricsRequest** | [**\Omnismith\Sdk\Model\IngestMetricsRequest**](../Model/IngestMetricsRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listEntityActions()`

```php
listEntityActions($id, $xOmnismithProjectId): \Omnismith\Sdk\Model\ListEntityActions200Response
```

List the actions available on an entity

The enabled actions of the entity's template, each evaluated against the record's current values.  Call this before changing a record: when an action exists for what you intend (a status transition, a hand-off), run it with `POST /entities/{id}/actions/{slug}` (the `execute_entity_action` tool) instead of a plain update (`update_entity`), so its presets and required fields apply.  Each entry says whether the action is `available` now and, if not, `unavailable_reason` names the attribute, the expectation and the current value. `fields` are the values to submit (keyed by `slug` in the execute body), with the list choices and reference target resolved; `presets` are what the action will set on its own.  Disabled actions are not listed. Read-only: nothing is written.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->listEntityActions($id, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->listEntityActions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ListEntityActions200Response**](../Model/ListEntityActions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `replaceEntity()`

```php
replaceEntity($id, $replaceEntityRequest, $xOmnismithProjectId)
```

Replace all non-metric attributes of an entity

Full replacement: after this call the entity's dimension attributes are exactly the map you sent. Every non-metric attribute of the template that is **absent from the map is cleared**. Use PATCH unless you really mean \"make the record look exactly like this\".  ### `attributes` An object keyed by attribute **slug or UUID** — mix them freely. Each value is a plain scalar, a backfill object `{ \"value\": ..., \"updated_at\": \"<RFC 3339>\" }`, or an operation object `{ \"op\": \"increment\", \"value\": <number> }`:  ```json {   \"hostname\": \"edge-fra-01\",   \"cpu_cores\": 8,   \"is_active\": true,   \"notes\": null,   \"01a094f1-24be-7154-a5bd-3b5c33c930fb\": \"01a094f1-4c1d-7498-b73b-48ae46da900b\",   \"operational_status\": { \"value\": \"Active\", \"updated_at\": \"2026-09-12T12:23:52Z\" },   \"restart_count\": { \"op\": \"increment\", \"value\": 1 } } ```  `null` clears an attribute. `{ \"op\": \"increment\", \"value\": n }` adds `n` to the stored number without you reading it first (number attributes and metrics only; concurrent increments never lose an update). Every attribute must belong to the entity's template and may appear only once (the same attribute as slug *and* UUID is rejected). Full value rules are on the `EntityAttributesInput` schema.  `attributes` is required; an explicit `{}` clears every non-metric attribute. Metric attributes are append-only telemetry and cannot be replaced — including one in the map is a `422`; send it via PATCH or `/entities/{id}/metrics`.  ### Errors - `400` — the body is not the documented shape (missing `attributes`, a list instead of an object, unknown fields, wrong types). - `422` — the shape is right but the content is not: unknown attribute, attribute not on the template, duplicate attribute, bad `updated_at`, a value that fails its attribute type, or an operation on an attribute that is not a number. `errors` names the exact field, e.g. `attributes.status`. - `404` — no entity with that id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$replaceEntityRequest = new \Omnismith\Sdk\Model\ReplaceEntityRequest(); // \Omnismith\Sdk\Model\ReplaceEntityRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->replaceEntity($id, $replaceEntityRequest, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->replaceEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **replaceEntityRequest** | [**\Omnismith\Sdk\Model\ReplaceEntityRequest**](../Model/ReplaceEntityRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchEntities()`

```php
searchEntities($templateId, $searchEntitiesRequest, $xOmnismithProjectId, $limit, $offset, $sortField, $sortDirection): \Omnismith\Sdk\Model\SearchEntities200Response
```

Search entities with filtering, sorting, and pagination

Executes structured queries, full-text searches, and sorting across dynamic entities of a specified template schema.  ### Template Targeting (`template_id`) Accepts either a canonical template UUID (e.g. `018b2f1b-8c1a...`) or a human-readable template slug (e.g. `product_catalog`).  ### Filters (`filter_groups`) A list of groups; clauses inside a group are AND-ed, groups are OR-ed. `[[a, b]]` is `a AND b`; `[[a], [b, c]]` is `a OR (b AND c)`; `[]` applies no filter. ```json [   [     {\"field\": \"status\", \"operator\": \"in\", \"value\": [\"018b…0020\", \"018b…0021\"]},     {\"field\": \"created_at\", \"operator\": \"between\", \"value\": [\"2026-01-01\", \"2026-03-31\"]},     {\"field\": \"customer.tier\", \"operator\": \"eq\", \"value\": \"018b…0042\"}   ],   [{\"field\": \"priority\", \"operator\": \"eq\", \"value\": \"018b…0007\"}] ] ``` - **`field`**: attribute slug or UUID, a standard field (`id`, `created_at`, `updated_at`), or a one-hop path `<reference>.<attribute>` that filters on an attribute of the referenced record (e.g. `customer.tier`). One hop only. - **`operator`** and **`value`**: `eq`, `neq`, `gt`, `lt`, `like` (case-insensitive substring), `not-like` take a string; `in`, `not-in` take a non-empty list of strings; `between` takes `[lower, upper]` (inclusive; number, date, datetime attributes and `created_at` / `updated_at`); `empty`, `not-empty` take no value. - List and reference attributes compare the stored id (from `list_item_ids` / `reference_entity_ids` or the schema), never the label. - Unknown fields, operators that do not fit the field, malformed values and paths that do not traverse a reference are refused with 400 naming the valid fields; a path into a template the caller may not view is 403.  ### Global Search (`global_search`) Performs accelerated full-text and GIN trigram matching across all string dimension attributes defined on the template.  ### Sorting & Pagination - **`sort_field`**: Attribute UUID, attribute slug, or standard entity fields (`id`, `created_at`, `updated_at`, `deleted_at`). - **`sort_direction`**: `asc` or `desc` (default: `asc` when `sort_field` is set, otherwise default sort is `created_at` DESC). - **`limit`** and **`offset`**: Bounded pagination (max 100 per page).  ### Attribute Values Shape (`verbose`) By default each record's `attribute_values` is a compact object mapping attribute slug to display value (UUID key when the attribute has no slug; empty values omitted). List, reference and file attributes show their label; the ids behind those labels come alongside in `list_item_ids`, `reference_entity_ids` and `file_ids` — filters and writes take those ids, not labels. Set `\"verbose\": true` in the request body to receive an array of `EntityAttributeValue` items with attribute `id`, `slug`, raw `value`, resolved `custom_value` and `reference_entity_id` instead.  ### Selective Field Projection (`fields`) By default, every matched entity is fully hydrated with all its attribute values. When querying large result sets or when only a subset of attributes is required, supply the `fields` array in the request body (e.g. `{\"fields\": [\"title\", \"status\"]}`). - **Selective Hydration**: Skips database value retrieval, reference lookups, list label resolution, and serialization for omitted attributes. - **Minimal Payload Volume**: Substantially reduces response payload size and network transfer overhead when reading multiple records. - **Root Metadata Guaranteed**: Essential entity identifiers and timestamps (`id`, `template_id`, `template_slug`, `created_at`, `updated_at`) are always preserved on every record. - **Self-Correcting Validation**: If an unrecognized field name is requested, the endpoint returns HTTP 400 Bad Request enumerating all valid attribute slugs and standard fields for the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = product_catalog; // string | Template UUID or human-readable template slug
$searchEntitiesRequest = new \Omnismith\Sdk\Model\SearchEntitiesRequest(); // \Omnismith\Sdk\Model\SearchEntitiesRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$limit = 50; // int | Maximum number of entity records to return (1-100)
$offset = 0; // int | Zero-based pagination offset
$sortField = created_at; // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)

try {
    $result = $apiInstance->searchEntities($templateId, $searchEntitiesRequest, $xOmnismithProjectId, $limit, $offset, $sortField, $sortDirection);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->searchEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Template UUID or human-readable template slug | |
| **searchEntitiesRequest** | [**\Omnismith\Sdk\Model\SearchEntitiesRequest**](../Model/SearchEntitiesRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **limit** | **int**| Maximum number of entity records to return (1-100) | [optional] [default to 50] |
| **offset** | **int**| Zero-based pagination offset | [optional] [default to 0] |
| **sortField** | **string**| Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [optional] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;asc&#39;] |

### Return type

[**\Omnismith\Sdk\Model\SearchEntities200Response**](../Model/SearchEntities200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `semanticSearchEntities()`

```php
semanticSearchEntities($semanticSearchEntitiesRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\SemanticSearchResultItem[]
```

Perform semantic vector similarity search on entities

Executes an approximate nearest neighbors (ANN) vector similarity search across entity dimension embeddings.  ### 768-Dimensional Embedding Vectors Requires a 768-dimensional float embedding array (`query_vector`) representing the query text or multimodal vector (e.g. generated by Google `text-embedding-004` or similar models).  ### Scoping & Filtering (`template_id`) Pass an optional `template_id` (UUID) or template slug to constrain the semantic search to records belonging to a specific template schema.  ### Cosine Similarity Threshold & Ranking (`threshold`) - `threshold`: Minimum cosine similarity score threshold (range `0.0` to `1.0`, default `0.5`). Observations below this similarity cutoff are discarded. - Matches are returned strictly ranked in descending order of `similarity_score`.  ### Attribute Values Shape (`verbose`) By default each nested entity's `attribute_values` is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in `list_item_ids`, `reference_entity_ids` and `file_ids`. Set `\"verbose\": true` to receive an array of `EntityAttributeValue` items with attribute `id`, `slug`, raw `value`, resolved `custom_value` and `reference_entity_id` instead.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$semanticSearchEntitiesRequest = new \Omnismith\Sdk\Model\SemanticSearchEntitiesRequest(); // \Omnismith\Sdk\Model\SemanticSearchEntitiesRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->semanticSearchEntities($semanticSearchEntitiesRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->semanticSearchEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **semanticSearchEntitiesRequest** | [**\Omnismith\Sdk\Model\SemanticSearchEntitiesRequest**](../Model/SemanticSearchEntitiesRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\SemanticSearchResultItem[]**](../Model/SemanticSearchResultItem.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateEntity()`

```php
updateEntity($id, $updateEntityRequest, $xOmnismithProjectId)
```

Update entity attribute values

Partial update: writes the attributes in the map and leaves every other attribute untouched. This is the default way to change an entity.  ### `attributes` An object keyed by attribute **slug or UUID** — mix them freely. Each value is a plain scalar, a backfill object `{ \"value\": ..., \"updated_at\": \"<RFC 3339>\" }`, or an operation object `{ \"op\": \"increment\", \"value\": <number> }`:  ```json {   \"hostname\": \"edge-fra-01\",   \"cpu_cores\": 8,   \"is_active\": true,   \"notes\": null,   \"01a094f1-24be-7154-a5bd-3b5c33c930fb\": \"01a094f1-4c1d-7498-b73b-48ae46da900b\",   \"operational_status\": { \"value\": \"Active\", \"updated_at\": \"2026-09-12T12:23:52Z\" },   \"restart_count\": { \"op\": \"increment\", \"value\": 1 } } ```  `null` clears an attribute. `{ \"op\": \"increment\", \"value\": n }` adds `n` to the stored number without you reading it first (number attributes and metrics only; concurrent increments never lose an update). Every attribute must belong to the entity's template and may appear only once (the same attribute as slug *and* UUID is rejected). Full value rules are on the `EntityAttributesInput` schema.  `attributes` is required and must not be empty. Dimension changes are appended to the entity's history (unchanged values cost nothing); metric attributes are appended to the entity's time series.  ### Errors - `400` — the body is not the documented shape (missing `attributes`, a list instead of an object, unknown fields, wrong types). - `422` — the shape is right but the content is not: unknown attribute, attribute not on the template, duplicate attribute, bad `updated_at`, a value that fails its attribute type, or an operation on an attribute that is not a number. `errors` names the exact field, e.g. `attributes.status`. - `404` — no entity with that id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$updateEntityRequest = new \Omnismith\Sdk\Model\UpdateEntityRequest(); // \Omnismith\Sdk\Model\UpdateEntityRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->updateEntity($id, $updateEntityRequest, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->updateEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **updateEntityRequest** | [**\Omnismith\Sdk\Model\UpdateEntityRequest**](../Model/UpdateEntityRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
