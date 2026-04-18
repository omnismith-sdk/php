# Omnismith\DashboardBlocksApi



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
createDashboardBlock($dashboard_id, $create_dashboard_block_request): \Omnismith\Model\CreateAttributeItem201Response
```

Create a new block in a dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboard_id = 'dashboard_id_example'; // string | Dashboard ID
$create_dashboard_block_request = new \Omnismith\Model\CreateDashboardBlockRequest(); // \Omnismith\Model\CreateDashboardBlockRequest

try {
    $result = $apiInstance->createDashboardBlock($dashboard_id, $create_dashboard_block_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->createDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboard_id** | **string**| Dashboard ID | |
| **create_dashboard_block_request** | [**\Omnismith\Model\CreateDashboardBlockRequest**](../Model/CreateDashboardBlockRequest.md)|  | |

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

## `deleteDashboardBlock()`

```php
deleteDashboardBlock($dashboard_id, $block_id)
```

Delete a dashboard block

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboard_id = 'dashboard_id_example'; // string | Dashboard ID
$block_id = 'block_id_example'; // string | Block ID

try {
    $apiInstance->deleteDashboardBlock($dashboard_id, $block_id);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->deleteDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboard_id** | **string**| Dashboard ID | |
| **block_id** | **string**| Block ID | |

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
getDashboardBlock($dashboard_id, $block_id): \Omnismith\Model\DashboardBlockResponse
```

Get a dashboard block by ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboard_id = 'dashboard_id_example'; // string | Dashboard ID
$block_id = 'block_id_example'; // string | Block ID

try {
    $result = $apiInstance->getDashboardBlock($dashboard_id, $block_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->getDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboard_id** | **string**| Dashboard ID | |
| **block_id** | **string**| Block ID | |

### Return type

[**\Omnismith\Model\DashboardBlockResponse**](../Model/DashboardBlockResponse.md)

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
listDashboardBlocks($dashboard_id): \Omnismith\Model\ListDashboardBlocks200Response
```

List all blocks in a dashboard

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboard_id = 'dashboard_id_example'; // string | Dashboard ID

try {
    $result = $apiInstance->listDashboardBlocks($dashboard_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->listDashboardBlocks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboard_id** | **string**| Dashboard ID | |

### Return type

[**\Omnismith\Model\ListDashboardBlocks200Response**](../Model/ListDashboardBlocks200Response.md)

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
resolveDashboardBlock($dashboard_id, $block_id): \Omnismith\Model\ResolvedBlockResponse
```

Resolve a dashboard block to its computed data

Executes the block configuration and returns computed values based on block type (stat count, gauge value, chart series, or list items)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboard_id = 'dashboard_id_example'; // string | Dashboard ID
$block_id = 'block_id_example'; // string | Block ID

try {
    $result = $apiInstance->resolveDashboardBlock($dashboard_id, $block_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->resolveDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboard_id** | **string**| Dashboard ID | |
| **block_id** | **string**| Block ID | |

### Return type

[**\Omnismith\Model\ResolvedBlockResponse**](../Model/ResolvedBlockResponse.md)

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
updateDashboardBlock($dashboard_id, $block_id, $update_dashboard_block_request)
```

Update a dashboard block

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\DashboardBlocksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboard_id = 'dashboard_id_example'; // string | Dashboard ID
$block_id = 'block_id_example'; // string | Block ID
$update_dashboard_block_request = new \Omnismith\Model\UpdateDashboardBlockRequest(); // \Omnismith\Model\UpdateDashboardBlockRequest

try {
    $apiInstance->updateDashboardBlock($dashboard_id, $block_id, $update_dashboard_block_request);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->updateDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboard_id** | **string**| Dashboard ID | |
| **block_id** | **string**| Block ID | |
| **update_dashboard_block_request** | [**\Omnismith\Model\UpdateDashboardBlockRequest**](../Model/UpdateDashboardBlockRequest.md)|  | |

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
