# Omnismith\Sdk\DashboardBlocksApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createDashboardBlock()**](DashboardBlocksApi.md#createDashboardBlock) | **POST** /dashboards/{dashboardId}/blocks | Create a new block in a dashboard |
| [**deleteDashboardBlock()**](DashboardBlocksApi.md#deleteDashboardBlock) | **DELETE** /dashboards/{dashboardId}/blocks/{blockId} | Delete a dashboard block |
| [**getDashboardBlock()**](DashboardBlocksApi.md#getDashboardBlock) | **GET** /dashboards/{dashboardId}/blocks/{blockId} | Get a dashboard block by ID |
| [**listDashboardBlocks()**](DashboardBlocksApi.md#listDashboardBlocks) | **GET** /dashboards/{dashboardId}/blocks | List all blocks in a dashboard |
| [**resolveDashboardBlock()**](DashboardBlocksApi.md#resolveDashboardBlock) | **GET** /dashboards/{dashboardId}/blocks/{blockId}/resolve | Resolve a dashboard block to its computed data |
| [**updateDashboardBlock()**](DashboardBlocksApi.md#updateDashboardBlock) | **PUT** /dashboards/{dashboardId}/blocks/{blockId} | Update a dashboard block |


## `createDashboardBlock()`

```php
createDashboardBlock($dashboardId, $createDashboardBlockRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Create a new block in a dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 'dashboardId_example'; // string | Dashboard ID
$createDashboardBlockRequest = new \Omnismith\Sdk\Model\CreateDashboardBlockRequest(); // \Omnismith\Sdk\Model\CreateDashboardBlockRequest

try {
    $result = $apiInstance->createDashboardBlock($dashboardId, $createDashboardBlockRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->createDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Dashboard ID | |
| **createDashboardBlockRequest** | [**\Omnismith\Sdk\Model\CreateDashboardBlockRequest**](../Model/CreateDashboardBlockRequest.md)|  | |

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

## `deleteDashboardBlock()`

```php
deleteDashboardBlock($dashboardId, $blockId)
```

Delete a dashboard block

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 'dashboardId_example'; // string | Dashboard ID
$blockId = 'blockId_example'; // string | Block ID

try {
    $apiInstance->deleteDashboardBlock($dashboardId, $blockId);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->deleteDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Dashboard ID | |
| **blockId** | **string**| Block ID | |

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

## `getDashboardBlock()`

```php
getDashboardBlock($dashboardId, $blockId): \Omnismith\Sdk\Model\DashboardBlockResponse
```

Get a dashboard block by ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 'dashboardId_example'; // string | Dashboard ID
$blockId = 'blockId_example'; // string | Block ID

try {
    $result = $apiInstance->getDashboardBlock($dashboardId, $blockId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->getDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Dashboard ID | |
| **blockId** | **string**| Block ID | |

### Return type

[**\Omnismith\Sdk\Model\DashboardBlockResponse**](../Model/DashboardBlockResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDashboardBlocks()`

```php
listDashboardBlocks($dashboardId): \Omnismith\Sdk\Model\ListDashboardBlocks200Response
```

List all blocks in a dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 'dashboardId_example'; // string | Dashboard ID

try {
    $result = $apiInstance->listDashboardBlocks($dashboardId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->listDashboardBlocks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Dashboard ID | |

### Return type

[**\Omnismith\Sdk\Model\ListDashboardBlocks200Response**](../Model/ListDashboardBlocks200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `resolveDashboardBlock()`

```php
resolveDashboardBlock($dashboardId, $blockId): \Omnismith\Sdk\Model\ResolvedBlockResponse
```

Resolve a dashboard block to its computed data

Executes the block configuration and returns computed values based on block type (stat count, gauge value, chart series, or list items)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 'dashboardId_example'; // string | Dashboard ID
$blockId = 'blockId_example'; // string | Block ID

try {
    $result = $apiInstance->resolveDashboardBlock($dashboardId, $blockId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->resolveDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Dashboard ID | |
| **blockId** | **string**| Block ID | |

### Return type

[**\Omnismith\Sdk\Model\ResolvedBlockResponse**](../Model/ResolvedBlockResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateDashboardBlock()`

```php
updateDashboardBlock($dashboardId, $blockId, $updateDashboardBlockRequest)
```

Update a dashboard block

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 'dashboardId_example'; // string | Dashboard ID
$blockId = 'blockId_example'; // string | Block ID
$updateDashboardBlockRequest = new \Omnismith\Sdk\Model\UpdateDashboardBlockRequest(); // \Omnismith\Sdk\Model\UpdateDashboardBlockRequest

try {
    $apiInstance->updateDashboardBlock($dashboardId, $blockId, $updateDashboardBlockRequest);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->updateDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Dashboard ID | |
| **blockId** | **string**| Block ID | |
| **updateDashboardBlockRequest** | [**\Omnismith\Sdk\Model\UpdateDashboardBlockRequest**](../Model/UpdateDashboardBlockRequest.md)|  | |

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
