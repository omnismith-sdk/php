# Omnismith\SavedQueriesApi

SavedQueries

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createSavedQuery()**](SavedQueriesApi.md#createSavedQuery) | **POST** /saved-queries | Create a saved query |
| [**deleteSavedQuery()**](SavedQueriesApi.md#deleteSavedQuery) | **DELETE** /saved-queries/{id} | Delete a saved query |
| [**executeSavedQuery()**](SavedQueriesApi.md#executeSavedQuery) | **POST** /saved-queries/{id}/execute | Execute a saved query (count matches) |
| [**getSavedQuery()**](SavedQueriesApi.md#getSavedQuery) | **GET** /saved-queries/{id} | Get a saved query |
| [**listSavedQueries()**](SavedQueriesApi.md#listSavedQueries) | **GET** /saved-queries | List saved queries |


## `createSavedQuery()`

```php
createSavedQuery($create_saved_query_request): \Omnismith\Model\CreateAttributeItem201Response
```

Create a saved query

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\SavedQueriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_saved_query_request = new \Omnismith\Model\CreateSavedQueryRequest(); // \Omnismith\Model\CreateSavedQueryRequest

try {
    $result = $apiInstance->createSavedQuery($create_saved_query_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SavedQueriesApi->createSavedQuery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_saved_query_request** | [**\Omnismith\Model\CreateSavedQueryRequest**](../Model/CreateSavedQueryRequest.md)|  | |

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

## `deleteSavedQuery()`

```php
deleteSavedQuery($id)
```

Delete a saved query

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\SavedQueriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteSavedQuery($id);
} catch (Exception $e) {
    echo 'Exception when calling SavedQueriesApi->deleteSavedQuery: ', $e->getMessage(), PHP_EOL;
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

## `executeSavedQuery()`

```php
executeSavedQuery($id): \Omnismith\Model\ExecuteSavedQuery200Response
```

Execute a saved query (count matches)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\SavedQueriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->executeSavedQuery($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SavedQueriesApi->executeSavedQuery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Omnismith\Model\ExecuteSavedQuery200Response**](../Model/ExecuteSavedQuery200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSavedQuery()`

```php
getSavedQuery($id): mixed
```

Get a saved query

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\SavedQueriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getSavedQuery($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SavedQueriesApi->getSavedQuery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

**mixed**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSavedQueries()`

```php
listSavedQueries(): \Omnismith\Model\ListSavedQueries200Response
```

List saved queries

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\SavedQueriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listSavedQueries();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SavedQueriesApi->listSavedQueries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\ListSavedQueries200Response**](../Model/ListSavedQueries200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
