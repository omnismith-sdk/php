# Omnismith\Sdk\DashboardsApi

Dashboards

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createDashboard()**](DashboardsApi.md#createDashboard) | **POST** /dashboards | Create a new dashboard |
| [**deleteDashboard()**](DashboardsApi.md#deleteDashboard) | **DELETE** /dashboards/{id} | Delete a dashboard |
| [**getDashboard()**](DashboardsApi.md#getDashboard) | **GET** /dashboards/{id} | Get a dashboard by ID |
| [**listDashboards()**](DashboardsApi.md#listDashboards) | **GET** /dashboards | List all dashboards |
| [**updateDashboard()**](DashboardsApi.md#updateDashboard) | **PUT** /dashboards/{id} | Update a dashboard |


## `createDashboard()`

```php
createDashboard($createDashboardRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Create a new dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createDashboardRequest = new \Omnismith\Sdk\Model\CreateDashboardRequest(); // \Omnismith\Sdk\Model\CreateDashboardRequest

try {
    $result = $apiInstance->createDashboard($createDashboardRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardsApi->createDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createDashboardRequest** | [**\Omnismith\Sdk\Model\CreateDashboardRequest**](../Model/CreateDashboardRequest.md)|  | |

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

## `deleteDashboard()`

```php
deleteDashboard($id)
```

Delete a dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Dashboard ID

try {
    $apiInstance->deleteDashboard($id);
} catch (Exception $e) {
    echo 'Exception when calling DashboardsApi->deleteDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Dashboard ID | |

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

## `getDashboard()`

```php
getDashboard($id): \Omnismith\Sdk\Model\DashboardResponse
```

Get a dashboard by ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Dashboard ID

try {
    $result = $apiInstance->getDashboard($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardsApi->getDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Dashboard ID | |

### Return type

[**\Omnismith\Sdk\Model\DashboardResponse**](../Model/DashboardResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDashboards()`

```php
listDashboards(): \Omnismith\Sdk\Model\ListDashboards200Response
```

List all dashboards

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listDashboards();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardsApi->listDashboards: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListDashboards200Response**](../Model/ListDashboards200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateDashboard()`

```php
updateDashboard($id, $updateDashboardRequest)
```

Update a dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Dashboard ID
$updateDashboardRequest = new \Omnismith\Sdk\Model\UpdateDashboardRequest(); // \Omnismith\Sdk\Model\UpdateDashboardRequest

try {
    $apiInstance->updateDashboard($id, $updateDashboardRequest);
} catch (Exception $e) {
    echo 'Exception when calling DashboardsApi->updateDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Dashboard ID | |
| **updateDashboardRequest** | [**\Omnismith\Sdk\Model\UpdateDashboardRequest**](../Model/UpdateDashboardRequest.md)|  | |

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
