# Omnismith\Sdk\EntityApi

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
createEntity($createEntityRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Create a new entity

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

[**\Omnismith\Sdk\Model\CreateAttributeItem201Response**](../Model/CreateAttributeItem201Response.md)

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
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityApi(
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
exportEntities($templateId, $exportEntitiesRequest, $sortField, $sortDirection): \SplFileObject
```

Export entities to CSV

Export entities matching the given filters to a CSV file. Uses the same filters as the search endpoint.

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
$templateId = 'templateId_example'; // string | Template ID
$exportEntitiesRequest = new \Omnismith\Sdk\Model\ExportEntitiesRequest(); // \Omnismith\Sdk\Model\ExportEntitiesRequest
$sortField = 'sortField_example'; // string | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at
$sortDirection = 'asc'; // string | Sort direction (only used when sort_field is provided)

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
| **templateId** | **string**| Template ID | |
| **exportEntitiesRequest** | [**\Omnismith\Sdk\Model\ExportEntitiesRequest**](../Model/ExportEntitiesRequest.md)|  | |
| **sortField** | **string**| Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at | [optional] |
| **sortDirection** | **string**| Sort direction (only used when sort_field is provided) | [optional] [default to &#39;asc&#39;] |

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
getEntity($id): \Omnismith\Sdk\Model\EntityResponse
```

Get an entity

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

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | Entity ID
$attributeIds = 'attributeIds_example'; // string | Comma-separated attribute IDs
$start = 56; // int | Start timestamp (Unix seconds)
$end = 56; // int | End timestamp (Unix seconds)
$aggregateFunc = 'avg'; // string | Aggregate function
$bucketWidth = '1 hour'; // string | Time bucket width (PostgreSQL interval)

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
| **id** | **string**| Entity ID | |
| **attributeIds** | **string**| Comma-separated attribute IDs | |
| **start** | **int**| Start timestamp (Unix seconds) | |
| **end** | **int**| End timestamp (Unix seconds) | |
| **aggregateFunc** | **string**| Aggregate function | [optional] [default to &#39;avg&#39;] |
| **bucketWidth** | **string**| Time bucket width (PostgreSQL interval) | [optional] [default to &#39;1 hour&#39;] |

### Return type

[**\Omnismith\Sdk\Model\GetEntityChart200Response**](../Model/GetEntityChart200Response.md)

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
getEntityHistory($id, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail): \Omnismith\Sdk\Model\GetEntityHistory200Response
```

Get entity history

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\EntityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | Entity ID
$page = 1; // int
$limit = 20; // int
$sortBy = 'created_at'; // string
$sortDirection = 'desc'; // string
$search = 'search_example'; // string
$attributeIds = 'attributeIds_example'; // string
$start = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter logs created after this timestamp
$end = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter logs created before this timestamp
$authorEmail = 'authorEmail_example'; // string | Filter logs by author email

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
| **id** | **string**| Entity ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **limit** | **int**|  | [optional] [default to 20] |
| **sortBy** | **string**|  | [optional] [default to &#39;created_at&#39;] |
| **sortDirection** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **search** | **string**|  | [optional] |
| **attributeIds** | **string**|  | [optional] |
| **start** | **\DateTime**| Filter logs created after this timestamp | [optional] |
| **end** | **\DateTime**| Filter logs created before this timestamp | [optional] |
| **authorEmail** | **string**| Filter logs by author email | [optional] |

### Return type

[**\Omnismith\Sdk\Model\GetEntityHistory200Response**](../Model/GetEntityHistory200Response.md)

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
importEntities($templateId, $file): \Omnismith\Sdk\Model\ImportEntities200Response
```

Import entities from CSV

Import entities from a CSV file. Supports upsert: creates new entities or updates existing ones based on the ID column. The CSV must include a metadata row (row 2) with attribute IDs prefixed by #.

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
$templateId = 'templateId_example'; // string | Template ID
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
| **templateId** | **string**| Template ID | |
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

## `searchEntities()`

```php
searchEntities($templateId, $searchEntitiesRequest, $limit, $offset, $sortField, $sortDirection): \Omnismith\Sdk\Model\SearchEntities200Response
```

Search entities

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
$templateId = 'templateId_example'; // string | Template ID
$searchEntitiesRequest = new \Omnismith\Sdk\Model\SearchEntitiesRequest(); // \Omnismith\Sdk\Model\SearchEntitiesRequest
$limit = 50; // int | Number of results
$offset = 0; // int | Pagination offset
$sortField = 'sortField_example'; // string | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at
$sortDirection = 'asc'; // string | Sort direction (only used when sort_field is provided)

try {
    $result = $apiInstance->searchEntities($templateId, $searchEntitiesRequest, $limit, $offset, $sortField, $sortDirection);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityApi->searchEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Template ID | |
| **searchEntitiesRequest** | [**\Omnismith\Sdk\Model\SearchEntitiesRequest**](../Model/SearchEntitiesRequest.md)|  | |
| **limit** | **int**| Number of results | [optional] [default to 50] |
| **offset** | **int**| Pagination offset | [optional] [default to 0] |
| **sortField** | **string**| Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at | [optional] |
| **sortDirection** | **string**| Sort direction (only used when sort_field is provided) | [optional] [default to &#39;asc&#39;] |

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

## `updateEntity()`

```php
updateEntity($id, $updateEntityRequest)
```

Update an entity

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
$id = 'id_example'; // string
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
| **id** | **string**|  | |
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
