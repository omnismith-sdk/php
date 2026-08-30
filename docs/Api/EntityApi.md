# Omnismith\Sdk\EntityApi

Entity

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createEntity()**](EntityApi.md#createEntity) | **POST** /entities | Create a new dynamic entity |
| [**deleteEntity()**](EntityApi.md#deleteEntity) | **DELETE** /entities/{id} | Soft-delete an entity record |
| [**exportEntities()**](EntityApi.md#exportEntities) | **POST** /entities/export/{template_id} | Export entities to structured CSV file |
| [**getEntity()**](EntityApi.md#getEntity) | **GET** /entities/{id} | Get an entity record by ID |
| [**getEntityChart()**](EntityApi.md#getEntityChart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory()**](EntityApi.md#getEntityHistory) | **GET** /entities/{id}/history | Get entity dimension change history |
| [**importEntities()**](EntityApi.md#importEntities) | **POST** /entities/import/{template_id} | Import entities from structured CSV file |
| [**ingestEntityMetrics()**](EntityApi.md#ingestEntityMetrics) | **POST** /entities/{id}/metrics | Ingest high-frequency metric observations for an entity |
| [**searchEntities()**](EntityApi.md#searchEntities) | **POST** /entities/search/{template_id} | Search entities with filtering, sorting, and pagination |
| [**semanticSearchEntities()**](EntityApi.md#semanticSearchEntities) | **POST** /entities/semantic-search | Perform semantic vector similarity search on entities |
| [**updateEntity()**](EntityApi.md#updateEntity) | **PATCH** /entities/{id} | Update entity attribute values |


## `createEntity()`

```php
createEntity($createEntityRequest): \Omnismith\Sdk\Model\CreateEntity201Response
```

Create a new dynamic entity

Creates a new dynamic entity record conforming to a template schema.  ### Template Association Specify the target schema via either `template_id` (UUID) or `template_slug` (human-readable slug).  ### Dynamic Attribute Values (`attribute_values`) Each attribute entry supports identifier resolution and accepts either: - `attribute_id`: Canonical attribute UUID - `attribute_slug`: Attribute slug identifier (e.g. `price`, `sku`, `status`)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value (e.g., `\"Wireless Headphones\"`) - **Dimension - Number**: Numeric string representation (e.g., `\"129.99\"`, `\"42\"`) - **Dimension - Boolean**: Strict boolean representation: `\"true\"`, `\"false\"`, `\"1\"`, or `\"0\"` - **Dimension - Date & Datetime**: Formatted as `YYYY-MM-DD` (date) or `YYYY-MM-DD HH:MM:SS` / ISO 8601 `YYYY-MM-DDTHH:MM:SSZ` (datetime) - **Dimension - File & Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined `ListItem` option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced `Entity`  ### Metric Telemetry Persistence Any metric attributes included in `attribute_values` are published directly to the metric ingestion pipeline and recorded in time-series telemetry storage.

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
$createEntityRequest = new \Omnismith\Sdk\Model\CreateEntityRequest(); // \Omnismith\Sdk\Model\CreateEntityRequest

try {
    $result = $apiInstance->createEntity($createEntityRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->createEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createEntityRequest** | [**\Omnismith\Sdk\Model\CreateEntityRequest**](../Model/CreateEntityRequest.md)|  | |

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
deleteEntity($id)
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

try {
    $apiInstance->deleteEntity($id);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->deleteEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) to soft-delete | |

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

## `exportEntities()`

```php
exportEntities($templateId, $exportEntitiesRequest, $sortField, $sortDirection): \SplFileObject
```

Export entities to structured CSV file

Exports entity records of a template schema matching filter criteria as a streaming CSV download.  ### Re-importable CSV Schema Format The generated CSV conforms to the Omnismith two-row metadata specification, making it directly compatible with `POST /entities/import/{template_id}`: - **Row 1**: Display column names and attribute aliases. - **Row 2**: Metadata row prefixed with `#` containing attribute UUIDs and column IDs (e.g. `#id`, `#018b2f1b-8c1a...`). - **Row 3+**: Entity data records.  ### Filter & Search Model Accepts the same filtering payload as `SearchEntities`: structured `filters` (supporting `eq`, `neq`, `gt`, `lt`, `like`, `not-like`, `empty`, `not-empty`) and `global_search` text queries.  ### Sorting Sort results via `sort_field` (attribute UUID, slug, or standard timestamp) and `sort_direction` (`asc`/`desc`).

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
$sortField = created_at; // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by
$sortDirection = asc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)

try {
    $result = $apiInstance->exportEntities($templateId, $exportEntitiesRequest, $sortField, $sortDirection);
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
getEntity($id, $attributeKey): \Omnismith\Sdk\Model\EntityResponse
```

Get an entity record by ID

Retrieves the full hydrated record for a dynamic entity by its unique identifier (UUID).  ### Attribute Key Formatting (`attribute_key`) The `attribute_key` query parameter controls the dictionary keys in `attribute_values`: - `\"id\"` (default): Keys are canonical attribute UUIDs (e.g. `018b2f1b-8c1a...`). - `\"slug\"`: Keys are human-readable attribute slugs (e.g. `price`, `sku`, `category`), which is recommended for API consumers and AI agent workflows.  ### Hydrated Attribute Values The returned `attribute_values` object includes both raw serialized values and resolved display labels (`custom_value`) for references and list options.

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
$attributeKey = slug; // string | Format for attribute_values dictionary keys: \"id\" for attribute UUIDs or \"slug\" for human-readable attribute slugs

try {
    $result = $apiInstance->getEntity($id, $attributeKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **attributeKey** | **string**| Format for attribute_values dictionary keys: \&quot;id\&quot; for attribute UUIDs or \&quot;slug\&quot; for human-readable attribute slugs | [optional] [default to &#39;id&#39;] |

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
getEntityChart($id, $attributeIds, $start, $end, $aggregateFunc, $bucketWidth): \Omnismith\Sdk\Model\GetEntityChart200Response
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
$aggregateFunc = avg; // string | Aggregation function applied within each bucket
$bucketWidth = 1 hour; // string | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day)

try {
    $result = $apiInstance->getEntityChart($id, $attributeIds, $start, $end, $aggregateFunc, $bucketWidth);
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
getEntityHistory($id, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail): \Omnismith\Sdk\Model\GetEntityHistory200Response
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
    $result = $apiInstance->getEntityHistory($id, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntityHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
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
importEntities($templateId, $file): \Omnismith\Sdk\Model\ImportEntities200Response
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

try {
    $result = $apiInstance->importEntities($templateId, $file);
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
ingestEntityMetrics($id, $ingestMetricsRequest)
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

try {
    $apiInstance->ingestEntityMetrics($id, $ingestMetricsRequest);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->ingestEntityMetrics: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **ingestMetricsRequest** | [**\Omnismith\Sdk\Model\IngestMetricsRequest**](../Model/IngestMetricsRequest.md)|  | |

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
searchEntities($templateId, $searchEntitiesRequest, $limit, $offset, $sortField, $sortDirection, $attributeKey): \Omnismith\Sdk\Model\SearchEntities200Response
```

Search entities with filtering, sorting, and pagination

Executes structured queries, full-text searches, and sorting across dynamic entities of a specified template schema.  ### Template Targeting (`template_id`) Accepts either a canonical template UUID (e.g. `018b2f1b-8c1a...`) or a human-readable template slug (e.g. `product_catalog`).  ### Structured Filters (`filters`) Filter conditions are specified in the request body as an array of filter objects: ```json [   {\"field\": \"status\", \"operator\": \"eq\", \"value\": \"018b2f1b-8c1a-75b3-8000-7f0000010020\"},   {\"field\": \"price\", \"operator\": \"gt\", \"value\": \"100\"},   {\"field\": \"name\", \"operator\": \"like\", \"value\": \"Pro\"} ] ``` - **`field`**: Target attribute UUID, attribute slug, or standard field (`id`, `created_at`, `updated_at`). - **`operator`**: Comparison operator: `eq` (equals), `neq` (not equals), `gt` (greater than), `lt` (less than), `like` (substring / trigram match), `not-like` (does not match), `empty` (is null or empty), `not-empty` (has value). - **`value`**: Target comparison value serialized as string.  ### Global Search (`global_search`) Performs accelerated full-text and GIN trigram matching across all string dimension attributes defined on the template.  ### Sorting & Pagination - **`sort_field`**: Attribute UUID, attribute slug, or standard entity fields (`id`, `created_at`, `updated_at`, `deleted_at`). - **`sort_direction`**: `asc` or `desc` (default: `asc` when `sort_field` is set, otherwise default sort is `created_at` DESC). - **`limit`** and **`offset`**: Bounded pagination (max 100 per page).  ### Attribute Key Formatting (`attribute_key`) Passing `attribute_key=\"slug\"` formats the returned `attribute_values` dictionary keys using human-readable attribute slugs instead of raw UUIDs.

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
$limit = 50; // int | Maximum number of entity records to return (1-100)
$offset = 0; // int | Zero-based pagination offset
$sortField = created_at; // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)
$attributeKey = slug; // string | Format for attribute_values dictionary keys: \"id\" for attribute UUIDs or \"slug\" for human-readable attribute slugs

try {
    $result = $apiInstance->searchEntities($templateId, $searchEntitiesRequest, $limit, $offset, $sortField, $sortDirection, $attributeKey);
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
| **limit** | **int**| Maximum number of entity records to return (1-100) | [optional] [default to 50] |
| **offset** | **int**| Zero-based pagination offset | [optional] [default to 0] |
| **sortField** | **string**| Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [optional] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;asc&#39;] |
| **attributeKey** | **string**| Format for attribute_values dictionary keys: \&quot;id\&quot; for attribute UUIDs or \&quot;slug\&quot; for human-readable attribute slugs | [optional] [default to &#39;id&#39;] |

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
semanticSearchEntities($semanticSearchEntitiesRequest): \Omnismith\Sdk\Model\SemanticSearchResultItem[]
```

Perform semantic vector similarity search on entities

Executes an approximate nearest neighbors (ANN) vector similarity search across entity dimension embeddings.  ### 768-Dimensional Embedding Vectors Requires a 768-dimensional float embedding array (`query_vector`) representing the query text or multimodal vector (e.g. generated by Google `text-embedding-004` or similar models).  ### Scoping & Filtering (`template_id`) Pass an optional `template_id` (UUID) or template slug to constrain the semantic search to records belonging to a specific template schema.  ### Cosine Similarity Threshold & Ranking (`threshold`) - `threshold`: Minimum cosine similarity score threshold (range `0.0` to `1.0`, default `0.5`). Observations below this similarity cutoff are discarded. - Matches are returned strictly ranked in descending order of `similarity_score`.  ### Attribute Key Formatting (`attribute_key`) Set `attribute_key=\"slug\"` to format the nested entity `attribute_values` dictionary keys as human-readable slugs instead of raw attribute UUIDs.

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

try {
    $result = $apiInstance->semanticSearchEntities($semanticSearchEntitiesRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->semanticSearchEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **semanticSearchEntitiesRequest** | [**\Omnismith\Sdk\Model\SemanticSearchEntitiesRequest**](../Model/SemanticSearchEntitiesRequest.md)|  | |

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
updateEntity($id, $updateEntityRequest)
```

Update entity attribute values

Updates specific dynamic attribute values for an existing entity record.  ### Dynamic Attribute Values (`attribute_values`) Submit one or more attribute value updates. Each entry supports identifier resolution via: - `attribute_id`: Canonical attribute UUID - `attribute_slug`: Attribute slug identifier (e.g. `price`, `sku`, `status`)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value - **Dimension - Number**: Numeric string representation (e.g. `\"149.99\"`) - **Dimension - Boolean**: Boolean representation: `\"true\"`, `\"false\"`, `\"1\"`, or `\"0\"` - **Dimension - Date & Datetime**: Formatted as `YYYY-MM-DD` or `YYYY-MM-DD HH:MM:SS` / ISO 8601 `YYYY-MM-DDTHH:MM:SSZ` - **Dimension - File & Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined `ListItem` option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced `Entity`  ### Audit Trail & Metrics - Dimension updates are recorded in the append-only entity dimension change history log. - Metric attribute values submitted here are dispatched to the metric streaming pipeline for time-series aggregation.

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

try {
    $apiInstance->updateEntity($id, $updateEntityRequest);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->updateEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **updateEntityRequest** | [**\Omnismith\Sdk\Model\UpdateEntityRequest**](../Model/UpdateEntityRequest.md)|  | |

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
