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
createDashboardBlock($dashboardId, $createDashboardBlockRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\CreateDashboardBlock201Response
```

Create a new block in a dashboard

Creates a new visualization block widget on a dashboard canvas. Supports four block types: stat (single KPI counter of matching entities), chart (time-series telemetry multi-line/bar graph aggregating metric data), gauge (metric threshold gauge with min/max bounds and percentage progress), and list (filtered and sorted entity table). Grid placement is defined via x, y, cols, rows layout parameters.

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
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Target dashboard unique identifier (UUID)
$createDashboardBlockRequest = new \Omnismith\Sdk\Model\CreateDashboardBlockRequest(); // \Omnismith\Sdk\Model\CreateDashboardBlockRequest | Dashboard block creation payload
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->createDashboardBlock($dashboardId, $createDashboardBlockRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->createDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Target dashboard unique identifier (UUID) | |
| **createDashboardBlockRequest** | [**\Omnismith\Sdk\Model\CreateDashboardBlockRequest**](../Model/CreateDashboardBlockRequest.md)| Dashboard block creation payload | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\CreateDashboardBlock201Response**](../Model/CreateDashboardBlock201Response.md)

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
deleteDashboardBlock($dashboardId, $blockId, $xOmnismithProjectId)
```

Delete a dashboard block

Permanently removes a visualization block widget from the specified dashboard canvas.

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
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID) to delete
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->deleteDashboardBlock($dashboardId, $blockId, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->deleteDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) to delete | |
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

## `getDashboardBlock()`

```php
getDashboardBlock($dashboardId, $blockId, $xOmnismithProjectId): \Omnismith\Sdk\Model\DashboardBlockResponse
```

Get a dashboard block by ID

Retrieves the configuration details, grid coordinates, and data query definitions for an individual visualization block.

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
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID)
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->getDashboardBlock($dashboardId, $blockId, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->getDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

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
listDashboardBlocks($dashboardId, $xOmnismithProjectId): \Omnismith\Sdk\Model\ListDashboardBlocks200Response
```

List all blocks in a dashboard

Retrieves all visualization blocks mounted on a dashboard canvas, including widget types (stat KPI card, time-series chart, gauge meter, entity list), grid position coordinates (x, y, cols, rows), template filters, and aggregation configs.

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
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->listDashboardBlocks($dashboardId, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->listDashboardBlocks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

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
resolveDashboardBlock($dashboardId, $blockId, $xOmnismithProjectId): \Omnismith\Sdk\Model\ResolvedBlockResponse
```

Resolve a dashboard block to its computed data

Executes the underlying data query for a dashboard block and returns computed real-time aggregated metrics and time-series telemetry. Returns a typed payload matching the block type: stat (matching entity count), gauge (current metric value, min/max bounds, progress percentage), chart (time-series data point series bucketed by time intervals with aggregation functions), or list (hydrated entity items with dynamic attributes).

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
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID) to resolve and compute
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->resolveDashboardBlock($dashboardId, $blockId, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->resolveDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) to resolve and compute | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

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
updateDashboardBlock($dashboardId, $blockId, $updateDashboardBlockRequest, $xOmnismithProjectId)
```

Update a dashboard block

Updates the display title, grid placement (x, y, cols, rows), metric queries, time-series aggregation buckets, gauge bounds, or filtering rules of an existing visualization block.

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
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID) to update
$updateDashboardBlockRequest = new \Omnismith\Sdk\Model\UpdateDashboardBlockRequest(); // \Omnismith\Sdk\Model\UpdateDashboardBlockRequest | Dashboard block update payload
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->updateDashboardBlock($dashboardId, $blockId, $updateDashboardBlockRequest, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling DashboardBlocksApi->updateDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) to update | |
| **updateDashboardBlockRequest** | [**\Omnismith\Sdk\Model\UpdateDashboardBlockRequest**](../Model/UpdateDashboardBlockRequest.md)| Dashboard block update payload | |
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
