# Omnismith\Sdk\ProjectsApi

Projects

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**assignUserToProject()**](ProjectsApi.md#assignUserToProject) | **POST** /projects/{id}/users | Assign user to project |
| [**createProject()**](ProjectsApi.md#createProject) | **POST** /projects | Create a new project |
| [**deleteProject()**](ProjectsApi.md#deleteProject) | **DELETE** /projects/{id} | Delete a project |
| [**dismissProjectTour()**](ProjectsApi.md#dismissProjectTour) | **POST** /projects/{id}/dismiss-tour | Dismiss the interactive tour for a project |
| [**getProject()**](ProjectsApi.md#getProject) | **GET** /projects/{id} | Get a project by ID |
| [**inviteUserToProject()**](ProjectsApi.md#inviteUserToProject) | **POST** /projects/{id}/users/invite | Invite user to project by email |
| [**listProjectUsers()**](ProjectsApi.md#listProjectUsers) | **GET** /projects/{id}/users | List users in project |
| [**listProjects()**](ProjectsApi.md#listProjects) | **GET** /projects | List all projects |
| [**removeUserFromProject()**](ProjectsApi.md#removeUserFromProject) | **DELETE** /projects/{id}/users/{userId} | Remove user from project |
| [**updateProject()**](ProjectsApi.md#updateProject) | **PUT** /projects/{id} | Update a project |


## `assignUserToProject()`

```php
assignUserToProject($id, $assignUserToProjectRequest)
```

Assign user to project

Assigns a user to a project with a specific role ID. Both the project and user must exist. Requires the caller to have project administration permissions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Project ID
$assignUserToProjectRequest = new \Omnismith\Sdk\Model\AssignUserToProjectRequest(); // \Omnismith\Sdk\Model\AssignUserToProjectRequest

try {
    $apiInstance->assignUserToProject($id, $assignUserToProjectRequest);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->assignUserToProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID | |
| **assignUserToProjectRequest** | [**\Omnismith\Sdk\Model\AssignUserToProjectRequest**](../Model/AssignUserToProjectRequest.md)|  | |

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

## `createProject()`

```php
createProject($createProjectRequest): \Omnismith\Sdk\Model\CreateProject201Response
```

Create a new project

Creates a new workspace project. A project is an isolated multi-tenant boundary grouping templates, attributes, entities, dashboards, and automations. An optional client-generated UUIDv7 `id` can be supplied.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createProjectRequest = new \Omnismith\Sdk\Model\CreateProjectRequest(); // \Omnismith\Sdk\Model\CreateProjectRequest

try {
    $result = $apiInstance->createProject($createProjectRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->createProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createProjectRequest** | [**\Omnismith\Sdk\Model\CreateProjectRequest**](../Model/CreateProjectRequest.md)|  | |

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

## `deleteProject()`

```php
deleteProject($id)
```

Delete a project

Soft-deletes a project and archives all associated entities, templates, attributes, and dashboards. Requires project owner permissions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Project ID to delete

try {
    $apiInstance->deleteProject($id);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->deleteProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID to delete | |

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

## `dismissProjectTour()`

```php
dismissProjectTour($id)
```

Dismiss the interactive tour for a project

Marks the interactive tour as dismissed for the given project, so it will not auto-trigger again.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique UUID identifier of the project

try {
    $apiInstance->dismissProjectTour($id);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->dismissProjectTour: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID identifier of the project | |

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

## `getProject()`

```php
getProject($id): \Omnismith\Sdk\Model\ProjectResponse
```

Get a project by ID

Retrieves details for a specific project by its UUID, including name, description, tour status, owner email, and timestamps.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Project ID

try {
    $result = $apiInstance->getProject($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->getProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID | |

### Return type

[**\Omnismith\Sdk\Model\ProjectResponse**](../Model/ProjectResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `inviteUserToProject()`

```php
inviteUserToProject($id, $inviteUserToProjectRequest)
```

Invite user to project by email

Invites a user to join a project using their email address. If the user exists, they are immediately assigned to the project with the specified role. If the user does not exist, a pending invitation will be created (future functionality).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Project ID
$inviteUserToProjectRequest = new \Omnismith\Sdk\Model\InviteUserToProjectRequest(); // \Omnismith\Sdk\Model\InviteUserToProjectRequest

try {
    $apiInstance->inviteUserToProject($id, $inviteUserToProjectRequest);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->inviteUserToProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID | |
| **inviteUserToProjectRequest** | [**\Omnismith\Sdk\Model\InviteUserToProjectRequest**](../Model/InviteUserToProjectRequest.md)|  | |

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

## `listProjectUsers()`

```php
listProjectUsers($id): \Omnismith\Sdk\Model\ListProjectUsers200Response
```

List users in project

Returns all users assigned to the specified project along with their roles (Admin, Editor, Viewer, etc.), email addresses, and join dates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Project ID

try {
    $result = $apiInstance->listProjectUsers($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->listProjectUsers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID | |

### Return type

[**\Omnismith\Sdk\Model\ListProjectUsers200Response**](../Model/ListProjectUsers200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listProjects()`

```php
listProjects(): \Omnismith\Sdk\Model\ListProjects200Response
```

List all projects

Returns all projects accessible to the authenticated user, including their assigned role and owner information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listProjects();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->listProjects: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListProjects200Response**](../Model/ListProjects200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeUserFromProject()`

```php
removeUserFromProject($id, $userId)
```

Remove user from project

Removes a user membership from the project. The user will immediately lose access to the project's data.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Project ID
$userId = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | User ID to remove from project

try {
    $apiInstance->removeUserFromProject($id, $userId);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->removeUserFromProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID | |
| **userId** | **string**| User ID to remove from project | |

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

## `updateProject()`

```php
updateProject($id, $updateProjectRequest)
```

Update a project

Updates project metadata such as name and description. Requires project administrator permissions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Project ID
$updateProjectRequest = new \Omnismith\Sdk\Model\UpdateProjectRequest(); // \Omnismith\Sdk\Model\UpdateProjectRequest

try {
    $apiInstance->updateProject($id, $updateProjectRequest);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->updateProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Project ID | |
| **updateProjectRequest** | [**\Omnismith\Sdk\Model\UpdateProjectRequest**](../Model/UpdateProjectRequest.md)|  | |

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
