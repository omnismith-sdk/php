# Omnismith\EntityApi

Entity

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createEntity()**](EntityApi.md#createEntity) | **POST** /entities | Create a new entity |
| [**deleteEntity()**](EntityApi.md#deleteEntity) | **DELETE** /entities/{id} | Delete an entity |
| [**exportEntities()**](EntityApi.md#exportEntities) | **POST** /entities/export/{template_id} | Export entities to CSV |
| [**getEntity()**](EntityApi.md#getEntity) | **GET** /entities/{id} | Get an entity |
| [**getEntityChart()**](EntityApi.md#getEntityChart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory()**](EntityApi.md#getEntityHistory) | **GET** /entities/{id}/history | Get entity history |
| [**importEntities()**](EntityApi.md#importEntities) | **POST** /entities/import/{template_id} | Import entities from CSV |
| [**searchEntities()**](EntityApi.md#searchEntities) | **POST** /entities/search/{template_id} | Search entities |
| [**updateEntity()**](EntityApi.md#updateEntity) | **PUT** /entities/{id} | Update an entity |


## `createEntity()`

```php
createEntity($create_entity_request): \Omnismith\Model\CreateAttributeItem201Response
```

Create a new entity

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_entity_request = new \Omnismith\Model\CreateEntityRequest(); // \Omnismith\Model\CreateEntityRequest

try {
    $result = $apiInstance->createEntity($create_entity_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->createEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_entity_request** | [**\Omnismith\Model\CreateEntityRequest**](../Model/CreateEntityRequest.md)|  | |

### Return type

[**\Omnismith\Model\CreateAttributeItem201Response**](../Model/CreateAttributeItem201Response.md)

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

Delete an entity

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteEntity($id);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->deleteEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `exportEntities()`

```php
exportEntities($template_id, $export_entities_request, $sort_field, $sort_direction): \SplFileObject
```

Export entities to CSV

Export entities matching the given filters to a CSV file. Uses the same filters as the search endpoint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 'template_id_example'; // string | Template ID
$export_entities_request = new \Omnismith\Model\ExportEntitiesRequest(); // \Omnismith\Model\ExportEntitiesRequest
$sort_field = 'sort_field_example'; // string | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at
$sort_direction = 'asc'; // string | Sort direction (only used when sort_field is provided)

try {
    $result = $apiInstance->exportEntities($template_id, $export_entities_request, $sort_field, $sort_direction);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->exportEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Template ID | |
| **export_entities_request** | [**\Omnismith\Model\ExportEntitiesRequest**](../Model/ExportEntitiesRequest.md)|  | |
| **sort_field** | **string**| Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at | [optional] |
| **sort_direction** | **string**| Sort direction (only used when sort_field is provided) | [optional] [default to &#39;asc&#39;] |

### Return type

**\SplFileObject**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `text/csv`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntity()`

```php
getEntity($id): \Omnismith\Model\EntityResponse
```

Get an entity

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getEntity($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Omnismith\Model\EntityResponse**](../Model/EntityResponse.md)

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
getEntityChart($id, $attribute_ids, $start, $end, $aggregate_func, $bucket_width): \Omnismith\Model\GetEntityChart200Response
```

Get entity chart time-series data

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | Entity ID
$attribute_ids = 'attribute_ids_example'; // string | Comma-separated attribute IDs
$start = 56; // int | Start timestamp (Unix seconds)
$end = 56; // int | End timestamp (Unix seconds)
$aggregate_func = 'avg'; // string | Aggregate function
$bucket_width = '1 hour'; // string | Time bucket width (PostgreSQL interval)

try {
    $result = $apiInstance->getEntityChart($id, $attribute_ids, $start, $end, $aggregate_func, $bucket_width);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntityChart: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Entity ID | |
| **attribute_ids** | **string**| Comma-separated attribute IDs | |
| **start** | **int**| Start timestamp (Unix seconds) | |
| **end** | **int**| End timestamp (Unix seconds) | |
| **aggregate_func** | **string**| Aggregate function | [optional] [default to &#39;avg&#39;] |
| **bucket_width** | **string**| Time bucket width (PostgreSQL interval) | [optional] [default to &#39;1 hour&#39;] |

### Return type

[**\Omnismith\Model\GetEntityChart200Response**](../Model/GetEntityChart200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntityHistory()`

```php
getEntityHistory($id, $page, $limit, $sort_by, $sort_direction, $search, $attribute_ids, $start, $end, $author_email): \Omnismith\Model\GetEntityHistory200Response
```

Get entity history

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | Entity ID
$page = 1; // int
$limit = 20; // int
$sort_by = 'created_at'; // string
$sort_direction = 'desc'; // string
$search = 'search_example'; // string
$attribute_ids = 'attribute_ids_example'; // string
$start = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter logs created after this timestamp
$end = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter logs created before this timestamp
$author_email = 'author_email_example'; // string | Filter logs by author email

try {
    $result = $apiInstance->getEntityHistory($id, $page, $limit, $sort_by, $sort_direction, $search, $attribute_ids, $start, $end, $author_email);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->getEntityHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Entity ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **limit** | **int**|  | [optional] [default to 20] |
| **sort_by** | **string**|  | [optional] [default to &#39;created_at&#39;] |
| **sort_direction** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **search** | **string**|  | [optional] |
| **attribute_ids** | **string**|  | [optional] |
| **start** | **\DateTime**| Filter logs created after this timestamp | [optional] |
| **end** | **\DateTime**| Filter logs created before this timestamp | [optional] |
| **author_email** | **string**| Filter logs by author email | [optional] |

### Return type

[**\Omnismith\Model\GetEntityHistory200Response**](../Model/GetEntityHistory200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `importEntities()`

```php
importEntities($template_id, $file): \Omnismith\Model\ImportEntities200Response
```

Import entities from CSV

Import entities from a CSV file. Supports upsert: creates new entities or updates existing ones based on the ID column. The CSV must include a metadata row (row 2) with attribute IDs prefixed by #.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 'template_id_example'; // string | Template ID
$file = '/path/to/file.txt'; // \SplFileObject | CSV file exported from the export endpoint or matching its format

try {
    $result = $apiInstance->importEntities($template_id, $file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->importEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Template ID | |
| **file** | **\SplFileObject****\SplFileObject**| CSV file exported from the export endpoint or matching its format | |

### Return type

[**\Omnismith\Model\ImportEntities200Response**](../Model/ImportEntities200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchEntities()`

```php
searchEntities($template_id, $search_entities_request, $limit, $offset, $sort_field, $sort_direction): \Omnismith\Model\SearchEntities200Response
```

Search entities

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 'template_id_example'; // string | Template ID
$search_entities_request = new \Omnismith\Model\SearchEntitiesRequest(); // \Omnismith\Model\SearchEntitiesRequest
$limit = 50; // int | Number of results
$offset = 0; // int | Pagination offset
$sort_field = 'sort_field_example'; // string | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at
$sort_direction = 'asc'; // string | Sort direction (only used when sort_field is provided)

try {
    $result = $apiInstance->searchEntities($template_id, $search_entities_request, $limit, $offset, $sort_field, $sort_direction);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->searchEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Template ID | |
| **search_entities_request** | [**\Omnismith\Model\SearchEntitiesRequest**](../Model/SearchEntitiesRequest.md)|  | |
| **limit** | **int**| Number of results | [optional] [default to 50] |
| **offset** | **int**| Pagination offset | [optional] [default to 0] |
| **sort_field** | **string**| Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at | [optional] |
| **sort_direction** | **string**| Sort direction (only used when sort_field is provided) | [optional] [default to &#39;asc&#39;] |

### Return type

[**\Omnismith\Model\SearchEntities200Response**](../Model/SearchEntities200Response.md)

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
updateEntity($id, $update_entity_request)
```

Update an entity

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_entity_request = new \Omnismith\Model\UpdateEntityRequest(); // \Omnismith\Model\UpdateEntityRequest

try {
    $apiInstance->updateEntity($id, $update_entity_request);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->updateEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_entity_request** | [**\Omnismith\Model\UpdateEntityRequest**](../Model/UpdateEntityRequest.md)|  | |

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
