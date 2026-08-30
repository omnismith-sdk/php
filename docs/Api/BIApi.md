# Omnismith\Sdk\BIApi

BI

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBiSchema()**](BIApi.md#getBiSchema) | **GET** /bi/schema | Get BI schema catalog |
| [**listBiTemplateRows()**](BIApi.md#listBiTemplateRows) | **POST** /bi/templates/{template_id}/rows | List flattened template rows for BI integration |
| [**listBiTemplateTimeSeries()**](BIApi.md#listBiTemplateTimeSeries) | **POST** /bi/templates/{template_id}/time-series | List aggregated time-series rows for BI integration |


## `getBiSchema()`

```php
getBiSchema(): \Omnismith\Sdk\Model\BiSchemaResponse
```

Get BI schema catalog

Returns a normalized metadata catalog of all template schemas and dynamic attribute definitions in the current workspace context.  ### BI Tooling Compatibility Designed for BI connectors (PowerBI, Tableau, Looker Studio, Metabase) and ETL ingestion pipelines. Translates dynamic template schemas into relational column definitions, data types (`string`, `number`, `boolean`, `datetime`, `date`), reference join keys, and allowed list options.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\BIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getBiSchema();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BIApi->getBiSchema: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\BiSchemaResponse**](../Model/BiSchemaResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listBiTemplateRows()`

```php
listBiTemplateRows($templateId, $biListTemplateRowsRequest, $limit, $offset, $sortField, $sortDirection): \Omnismith\Sdk\Model\BiTemplateRowsResponse
```

List flattened template rows for BI integration

Returns a flattened, relational row-based live dataset for a template, optimized for BI dashboards, spreadsheets, and reporting tools.  ### Tabular Data Model Transforms dynamic entity records into flat rows where columns correspond to the attribute definitions retrieved from `GET /bi/schema`.  ### Filter & Search Model Supports structured `filters` (operators: `eq`, `neq`, `gt`, `lt`, `like`, `not-like`, `empty`, `not-empty`) and `global_search` text queries.  ### Sorting & Pagination - `sort_field`: Attribute UUID, slug, or standard column (`id`, `created_at`, `updated_at`, `deleted_at`). - `sort_direction`: `asc` or `desc`. - `limit` (max 100) and `offset` pagination.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\BIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010001; // string | Unique identifier (UUID) of the template schema to query
$biListTemplateRowsRequest = new \Omnismith\Sdk\Model\BiListTemplateRowsRequest(); // \Omnismith\Sdk\Model\BiListTemplateRowsRequest
$limit = 50; // int | Maximum number of rows to return per page (1-100)
$offset = 0; // int | Zero-based pagination offset
$sortField = created_at; // string | Attribute UUID, slug, or standard field (id, created_at, updated_at, deleted_at) to sort by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)

try {
    $result = $apiInstance->listBiTemplateRows($templateId, $biListTemplateRowsRequest, $limit, $offset, $sortField, $sortDirection);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BIApi->listBiTemplateRows: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Unique identifier (UUID) of the template schema to query | |
| **biListTemplateRowsRequest** | [**\Omnismith\Sdk\Model\BiListTemplateRowsRequest**](../Model/BiListTemplateRowsRequest.md)|  | |
| **limit** | **int**| Maximum number of rows to return per page (1-100) | [optional] [default to 50] |
| **offset** | **int**| Zero-based pagination offset | [optional] [default to 0] |
| **sortField** | **string**| Attribute UUID, slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [optional] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;asc&#39;] |

### Return type

[**\Omnismith\Sdk\Model\BiTemplateRowsResponse**](../Model/BiTemplateRowsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listBiTemplateTimeSeries()`

```php
listBiTemplateTimeSeries($templateId, $attributeIds, $start, $end, $biListTemplateRowsRequest, $aggregateFunc, $bucketWidth): \Omnismith\Sdk\Model\BiTimeSeriesResponse
```

List aggregated time-series rows for BI integration

Returns aggregated, time-bucketed metric data points across entities of a template schema for BI and analytical visualization tools.  ### Combined Dimension Filtering & Metric Aggregation Combines entity dimension filtering (scoped via the `filters` and `global_search` body payload) with time-series rollup across the specified `attribute_ids`.  ### Aggregation Functions (`aggregate_func`) - `avg` (default), `sum`, `min`, `max`, `count`, `first`, `last`.  ### Bucket Intervals (`bucket_width`) Values follow standard time interval notation: `1 second`, `5 seconds`, `10 seconds`, `1 minute` (1m), `5 minutes` (5m), `10 minutes`, `15 minutes`, `30 minutes`, `1 hour` (1h), `6 hours`, `12 hours`, `1 day` (1d), `1 week`, `1 month`.  ### Query Window (`start` & `end`) Specified as integer Unix epoch seconds bounding the telemetry observations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\BIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010001; // string | Unique identifier (UUID) of the template schema
$attributeIds = 018b2f1b-8c1a-75b3-8000-7f0000010010,018b2f1b-8c1a-75b3-8000-7f0000010011; // string | Comma-separated metric attribute UUIDs to aggregate
$start = 1774396800; // int | Start timestamp as Unix epoch in seconds
$end = 1774483200; // int | End timestamp as Unix epoch in seconds
$biListTemplateRowsRequest = new \Omnismith\Sdk\Model\BiListTemplateRowsRequest(); // \Omnismith\Sdk\Model\BiListTemplateRowsRequest
$aggregateFunc = avg; // string | Aggregation function applied within each time bucket
$bucketWidth = 1 hour; // string | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day)

try {
    $result = $apiInstance->listBiTemplateTimeSeries($templateId, $attributeIds, $start, $end, $biListTemplateRowsRequest, $aggregateFunc, $bucketWidth);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BIApi->listBiTemplateTimeSeries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Unique identifier (UUID) of the template schema | |
| **attributeIds** | **string**| Comma-separated metric attribute UUIDs to aggregate | |
| **start** | **int**| Start timestamp as Unix epoch in seconds | |
| **end** | **int**| End timestamp as Unix epoch in seconds | |
| **biListTemplateRowsRequest** | [**\Omnismith\Sdk\Model\BiListTemplateRowsRequest**](../Model/BiListTemplateRowsRequest.md)|  | |
| **aggregateFunc** | **string**| Aggregation function applied within each time bucket | [optional] [default to &#39;avg&#39;] |
| **bucketWidth** | **string**| Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) | [optional] [default to &#39;1 hour&#39;] |

### Return type

[**\Omnismith\Sdk\Model\BiTimeSeriesResponse**](../Model/BiTimeSeriesResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
