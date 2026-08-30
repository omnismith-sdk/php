# Omnismith\Sdk\WorkspacesApi

Workspaces

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createWorkspace()**](WorkspacesApi.md#createWorkspace) | **POST** /workspaces | Create a new workspace |
| [**createWorkspaceView()**](WorkspacesApi.md#createWorkspaceView) | **POST** /workspaces/{id}/views | Add a new view / pane to a workspace |
| [**deleteWorkspace()**](WorkspacesApi.md#deleteWorkspace) | **DELETE** /workspaces/{id} | Delete a workspace and its views |
| [**deleteWorkspaceView()**](WorkspacesApi.md#deleteWorkspaceView) | **DELETE** /workspaces/{id}/views/{viewId} | Delete a view / pane from a workspace |
| [**duplicateWorkspace()**](WorkspacesApi.md#duplicateWorkspace) | **POST** /workspaces/{id}/duplicate | Duplicate an existing workspace and its views |
| [**getWorkspace()**](WorkspacesApi.md#getWorkspace) | **GET** /workspaces/{id} | Get workspace details and its views |
| [**getWorkspaceView()**](WorkspacesApi.md#getWorkspaceView) | **GET** /workspaces/{id}/views/{viewId} | Get details of a workspace view / pane |
| [**listTemplateViews()**](WorkspacesApi.md#listTemplateViews) | **GET** /workspaces/template/{templateId} | List saved views for a specific template across workspaces |
| [**listWorkspaces()**](WorkspacesApi.md#listWorkspaces) | **GET** /workspaces | List all workspaces for current project |
| [**reorderWorkspaceViews()**](WorkspacesApi.md#reorderWorkspaceViews) | **PUT** /workspaces/{id}/reorder-views | Reorder views inside a workspace |
| [**setDefaultWorkspace()**](WorkspacesApi.md#setDefaultWorkspace) | **POST** /workspaces/{id}/default | Set workspace as the default workspace |
| [**updateWorkspace()**](WorkspacesApi.md#updateWorkspace) | **PUT** /workspaces/{id} | Update workspace metadata and layout |
| [**updateWorkspaceView()**](WorkspacesApi.md#updateWorkspaceView) | **PUT** /workspaces/{id}/views/{viewId} | Update workspace view / pane filters, sort, display mode, or columns |


## `createWorkspace()`

```php
createWorkspace($createWorkspaceRequest): \Omnismith\Sdk\Model\CreateDashboard201Response
```

Create a new workspace

Creates a new workspace in the current project context with a specified multi-pane layout (single, split-v, split-h, quad), optional default workspace status, and initial template view bindings to automatically generate panes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createWorkspaceRequest = new \Omnismith\Sdk\Model\CreateWorkspaceRequest(); // \Omnismith\Sdk\Model\CreateWorkspaceRequest | Workspace creation payload

try {
    $result = $apiInstance->createWorkspace($createWorkspaceRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createWorkspaceRequest** | [**\Omnismith\Sdk\Model\CreateWorkspaceRequest**](../Model/CreateWorkspaceRequest.md)| Workspace creation payload | |

### Return type

[**\Omnismith\Sdk\Model\CreateDashboard201Response**](../Model/CreateDashboard201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createWorkspaceView()`

```php
createWorkspaceView($id, $createWorkspaceViewRequest): \Omnismith\Sdk\Model\CreateDashboardBlock201Response
```

Add a new view / pane to a workspace

Creates and mounts a new view pane within an existing workspace bound to a specific entity schema template, configuring presentation mode (table, grid), visible columns, filter criteria, search queries (keyword or semantic), sorting preferences, and pane order.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Target workspace unique identifier (UUID)
$createWorkspaceViewRequest = new \Omnismith\Sdk\Model\CreateWorkspaceViewRequest(); // \Omnismith\Sdk\Model\CreateWorkspaceViewRequest | Workspace view creation payload

try {
    $result = $apiInstance->createWorkspaceView($id, $createWorkspaceViewRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Target workspace unique identifier (UUID) | |
| **createWorkspaceViewRequest** | [**\Omnismith\Sdk\Model\CreateWorkspaceViewRequest**](../Model/CreateWorkspaceViewRequest.md)| Workspace view creation payload | |

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

## `deleteWorkspace()`

```php
deleteWorkspace($id)
```

Delete a workspace and its views

Permanently removes a workspace and all nested view pane configurations from the project.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID) to delete

try {
    $apiInstance->deleteWorkspace($id);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->deleteWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) to delete | |

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

## `deleteWorkspaceView()`

```php
deleteWorkspaceView($id, $viewId)
```

Delete a view / pane from a workspace

Permanently removes a view pane from a workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$viewId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Workspace view unique identifier (UUID) to delete

try {
    $apiInstance->deleteWorkspaceView($id, $viewId);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->deleteWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **viewId** | **string**| Workspace view unique identifier (UUID) to delete | |

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

## `duplicateWorkspace()`

```php
duplicateWorkspace($id, $duplicateWorkspaceRequest): \Omnismith\Sdk\Model\DuplicateWorkspace201Response
```

Duplicate an existing workspace and its views

Creates a deep copy of an existing workspace, cloning all nested view panes, filter rules, display configurations, and layout settings into a new workspace with an optional customized name.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Source workspace unique identifier (UUID) to clone
$duplicateWorkspaceRequest = new \Omnismith\Sdk\Model\DuplicateWorkspaceRequest(); // \Omnismith\Sdk\Model\DuplicateWorkspaceRequest | Optional configuration for the duplicated workspace

try {
    $result = $apiInstance->duplicateWorkspace($id, $duplicateWorkspaceRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->duplicateWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Source workspace unique identifier (UUID) to clone | |
| **duplicateWorkspaceRequest** | [**\Omnismith\Sdk\Model\DuplicateWorkspaceRequest**](../Model/DuplicateWorkspaceRequest.md)| Optional configuration for the duplicated workspace | [optional] |

### Return type

[**\Omnismith\Sdk\Model\DuplicateWorkspace201Response**](../Model/DuplicateWorkspace201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspace()`

```php
getWorkspace($id): \Omnismith\Sdk\Model\WorkspaceDetailsResponse
```

Get workspace details and its views

Retrieves detailed information for a specific workspace, including its multi-pane layout configuration and all hydrated view panes with their associated template schemas, filter rules, search criteria, column selections, and ordering.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)

try {
    $result = $apiInstance->getWorkspace($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\WorkspaceDetailsResponse**](../Model/WorkspaceDetailsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspaceView()`

```php
getWorkspaceView($id, $viewId): \Omnismith\Sdk\Model\WorkspaceViewResponse
```

Get details of a workspace view / pane

Retrieves complete configuration details for a single workspace view pane, including its schema template binding, active filter rules, search parameters, column visibility, sort order, and layout positioning.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$viewId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Workspace view unique identifier (UUID)

try {
    $result = $apiInstance->getWorkspaceView($id, $viewId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **viewId** | **string**| Workspace view unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\WorkspaceViewResponse**](../Model/WorkspaceViewResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplateViews()`

```php
listTemplateViews($templateId): \Omnismith\Sdk\Model\ListTemplateViews200Response
```

List saved views for a specific template across workspaces

Searches and returns all saved workspace view panes configured across any workspace that are bound to a specific entity schema template, facilitating cross-workspace view reuse and discovery.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Schema template unique identifier (UUID)

try {
    $result = $apiInstance->listTemplateViews($templateId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listTemplateViews: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Schema template unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\ListTemplateViews200Response**](../Model/ListTemplateViews200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWorkspaces()`

```php
listWorkspaces(): \Omnismith\Sdk\Model\ListWorkspaces200Response
```

List all workspaces for current project

Retrieves all workspaces configured within the authenticated project context, including multi-pane layout structures (single, split-v, split-h, quad), view pane counts, sort ordering, and default workspace indicators for workbench navigation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listWorkspaces();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listWorkspaces: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListWorkspaces200Response**](../Model/ListWorkspaces200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `reorderWorkspaceViews()`

```php
reorderWorkspaceViews($id, $reorderWorkspaceViewsRequest)
```

Reorder views inside a workspace

Updates the visual sequence and tab ordering of view panes inside a workspace by supplying an ordered list of view IDs matching the desired layout arrangement.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$reorderWorkspaceViewsRequest = new \Omnismith\Sdk\Model\ReorderWorkspaceViewsRequest(); // \Omnismith\Sdk\Model\ReorderWorkspaceViewsRequest | Payload containing ordered view IDs

try {
    $apiInstance->reorderWorkspaceViews($id, $reorderWorkspaceViewsRequest);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->reorderWorkspaceViews: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **reorderWorkspaceViewsRequest** | [**\Omnismith\Sdk\Model\ReorderWorkspaceViewsRequest**](../Model/ReorderWorkspaceViewsRequest.md)| Payload containing ordered view IDs | |

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

## `setDefaultWorkspace()`

```php
setDefaultWorkspace($id)
```

Set workspace as the default workspace

Designates the specified workspace as the primary/default landing view for the project, automatically demoting any existing default workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID) to designate as default

try {
    $apiInstance->setDefaultWorkspace($id);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->setDefaultWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) to designate as default | |

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

## `updateWorkspace()`

```php
updateWorkspace($id, $updateWorkspaceRequest)
```

Update workspace metadata and layout

Updates workspace attributes including display name, description, multi-pane layout arrangement (single, split-v, split-h, quad), sort order sequence, and default workspace status.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID) to update
$updateWorkspaceRequest = new \Omnismith\Sdk\Model\UpdateWorkspaceRequest(); // \Omnismith\Sdk\Model\UpdateWorkspaceRequest | Workspace update payload

try {
    $apiInstance->updateWorkspace($id, $updateWorkspaceRequest);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->updateWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) to update | |
| **updateWorkspaceRequest** | [**\Omnismith\Sdk\Model\UpdateWorkspaceRequest**](../Model/UpdateWorkspaceRequest.md)| Workspace update payload | |

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

## `updateWorkspaceView()`

```php
updateWorkspaceView($id, $viewId, $updateWorkspaceViewRequest)
```

Update workspace view / pane filters, sort, display mode, or columns

Updates the configuration of a specific workspace view pane, modifying its title, filtering rules, search query and mode, sorting preferences, presentation display mode (table or grid), column visibility lists, or pane display sequence.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$viewId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Workspace view unique identifier (UUID) to update
$updateWorkspaceViewRequest = new \Omnismith\Sdk\Model\UpdateWorkspaceViewRequest(); // \Omnismith\Sdk\Model\UpdateWorkspaceViewRequest | Workspace view update payload

try {
    $apiInstance->updateWorkspaceView($id, $viewId, $updateWorkspaceViewRequest);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->updateWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **viewId** | **string**| Workspace view unique identifier (UUID) to update | |
| **updateWorkspaceViewRequest** | [**\Omnismith\Sdk\Model\UpdateWorkspaceViewRequest**](../Model/UpdateWorkspaceViewRequest.md)| Workspace view update payload | |

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
