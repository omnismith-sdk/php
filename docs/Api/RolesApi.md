# Omnismith\Sdk\RolesApi

Roles

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createRole()**](RolesApi.md#createRole) | **POST** /roles | Create a new role |
| [**deleteRole()**](RolesApi.md#deleteRole) | **DELETE** /roles/{id} | Delete a role |
| [**getRole()**](RolesApi.md#getRole) | **GET** /roles/{id} | Get a role |
| [**getRolePermissions()**](RolesApi.md#getRolePermissions) | **GET** /roles/{id}/permissions | Get role permissions |
| [**getRoleResources()**](RolesApi.md#getRoleResources) | **GET** /roles/{id}/resources | Get role resource restrictions |
| [**getRoleScopes()**](RolesApi.md#getRoleScopes) | **GET** /roles/{id}/scopes | Get role entity-access scopes |
| [**listAvailablePermissions()**](RolesApi.md#listAvailablePermissions) | **GET** /roles/permissions/available | List available permissions for role assignment |
| [**listRoles()**](RolesApi.md#listRoles) | **GET** /roles | List roles |
| [**setRolePermissions()**](RolesApi.md#setRolePermissions) | **PUT** /roles/{id}/permissions | Set role permissions |
| [**setRoleResources()**](RolesApi.md#setRoleResources) | **PUT** /roles/{id}/resources | Set role resource restrictions |
| [**setRoleScopes()**](RolesApi.md#setRoleScopes) | **PUT** /roles/{id}/scopes | Set role entity-access scopes |
| [**updateRole()**](RolesApi.md#updateRole) | **PUT** /roles/{id} | Update a role |


## `createRole()`

```php
createRole($createRoleRequest): \Omnismith\Sdk\Model\CreateProject201Response
```

Create a new role

Creates a new custom role within the project. Role permissions, resource restrictions, and entity scopes can be configured subsequently.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createRoleRequest = new \Omnismith\Sdk\Model\CreateRoleRequest(); // \Omnismith\Sdk\Model\CreateRoleRequest

try {
    $result = $apiInstance->createRole($createRoleRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->createRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createRoleRequest** | [**\Omnismith\Sdk\Model\CreateRoleRequest**](../Model/CreateRoleRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateProject201Response**](../Model/CreateProject201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteRole()`

```php
deleteRole($id)
```

Delete a role

Permanently deletes a custom role. System owner roles cannot be deleted. Any users assigned to this role must be reassigned.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role to delete

try {
    $apiInstance->deleteRole($id);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->deleteRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role to delete | |

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

## `getRole()`

```php
getRole($id): \Omnismith\Sdk\Model\RoleResponse
```

Get a role

Retrieves role metadata (name, is_owner status, creation timestamp) by role UUID.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role

try {
    $result = $apiInstance->getRole($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->getRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |

### Return type

[**\Omnismith\Sdk\Model\RoleResponse**](../Model/RoleResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRolePermissions()`

```php
getRolePermissions($id): \Omnismith\Sdk\Model\GetRolePermissions200Response
```

Get role permissions

Returns the array of permission keys (e.g. \"template.view\", \"entity.create\", \"attribute.manage\") explicitly granted to the specified role.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role

try {
    $result = $apiInstance->getRolePermissions($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->getRolePermissions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |

### Return type

[**\Omnismith\Sdk\Model\GetRolePermissions200Response**](../Model/GetRolePermissions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRoleResources()`

```php
getRoleResources($id): \Omnismith\Sdk\Model\GetRoleResources200Response
```

Get role resource restrictions

Retrieves granular resource-level access restrictions configured for the role, specifying access levels (deny, view, edit, full) for particular templates or attributes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role

try {
    $result = $apiInstance->getRoleResources($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->getRoleResources: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |

### Return type

[**\Omnismith\Sdk\Model\GetRoleResources200Response**](../Model/GetRoleResources200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRoleScopes()`

```php
getRoleScopes($id): \Omnismith\Sdk\Model\GetRoleScopes200Response
```

Get role entity-access scopes

Retrieves row-level entity access scopes for the role, which restrict what entity records matching specific attribute conditions the role can access within given templates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role

try {
    $result = $apiInstance->getRoleScopes($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->getRoleScopes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |

### Return type

[**\Omnismith\Sdk\Model\GetRoleScopes200Response**](../Model/GetRoleScopes200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAvailablePermissions()`

```php
listAvailablePermissions(): \Omnismith\Sdk\Model\ListAvailablePermissions200Response
```

List available permissions for role assignment

Returns all user-assignable permissions grouped by module. Excludes internal-only permissions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAvailablePermissions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->listAvailablePermissions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListAvailablePermissions200Response**](../Model/ListAvailablePermissions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRoles()`

```php
listRoles(): \Omnismith\Sdk\Model\ListRoles200Response
```

List roles

Lists all custom and predefined roles defined within the current project, including the project owner role.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listRoles();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->listRoles: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListRoles200Response**](../Model/ListRoles200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `setRolePermissions()`

```php
setRolePermissions($id, $setRolePermissionsRequest)
```

Set role permissions

Replaces the entire set of permission keys assigned to the role with the provided list. Use GET /roles/permissions/available to inspect valid keys.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role
$setRolePermissionsRequest = new \Omnismith\Sdk\Model\SetRolePermissionsRequest(); // \Omnismith\Sdk\Model\SetRolePermissionsRequest

try {
    $apiInstance->setRolePermissions($id, $setRolePermissionsRequest);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->setRolePermissions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |
| **setRolePermissionsRequest** | [**\Omnismith\Sdk\Model\SetRolePermissionsRequest**](../Model/SetRolePermissionsRequest.md)|  | |

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

## `setRoleResources()`

```php
setRoleResources($id, $setRoleResourcesRequest)
```

Set role resource restrictions

Replaces all resource-level access restrictions for the role. Each item defines a resource type (\"template\" or \"attribute\"), target resource UUID, and granted access level (\"deny\", \"view\", \"edit\", \"full\").

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role
$setRoleResourcesRequest = new \Omnismith\Sdk\Model\SetRoleResourcesRequest(); // \Omnismith\Sdk\Model\SetRoleResourcesRequest

try {
    $apiInstance->setRoleResources($id, $setRoleResourcesRequest);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->setRoleResources: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |
| **setRoleResourcesRequest** | [**\Omnismith\Sdk\Model\SetRoleResourcesRequest**](../Model/SetRoleResourcesRequest.md)|  | |

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

## `setRoleScopes()`

```php
setRoleScopes($id, $setRoleScopesRequest)
```

Set role entity-access scopes

Replaces row-level entity access scopes for the role. Conditions filter entity visibility based on field/attribute comparisons (operators: eq, neq, gt, lt, like, not-like, empty, not-empty).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role
$setRoleScopesRequest = new \Omnismith\Sdk\Model\SetRoleScopesRequest(); // \Omnismith\Sdk\Model\SetRoleScopesRequest

try {
    $apiInstance->setRoleScopes($id, $setRoleScopesRequest);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->setRoleScopes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |
| **setRoleScopesRequest** | [**\Omnismith\Sdk\Model\SetRoleScopesRequest**](../Model/SetRoleScopesRequest.md)|  | |

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

## `updateRole()`

```php
updateRole($id, $updateRoleRequest)
```

Update a role

Updates the display name of an existing custom role. System owner roles cannot be modified.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\RolesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID of the role
$updateRoleRequest = new \Omnismith\Sdk\Model\UpdateRoleRequest(); // \Omnismith\Sdk\Model\UpdateRoleRequest

try {
    $apiInstance->updateRole($id, $updateRoleRequest);
} catch (Exception $e) {
    echo 'Exception when calling RolesApi->updateRole: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the role | |
| **updateRoleRequest** | [**\Omnismith\Sdk\Model\UpdateRoleRequest**](../Model/UpdateRoleRequest.md)|  | |

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
