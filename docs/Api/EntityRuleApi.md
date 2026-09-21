# Omnismith\Sdk\EntityRuleApi

EntityRule

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTemplateRule()**](EntityRuleApi.md#createTemplateRule) | **POST** /templates/{templateId}/rules | Create a business rule on a template |
| [**deleteTemplateRule()**](EntityRuleApi.md#deleteTemplateRule) | **DELETE** /templates/{templateId}/rules/{id} | Delete a business rule |
| [**getTemplateRule()**](EntityRuleApi.md#getTemplateRule) | **GET** /templates/{templateId}/rules/{id} | Get a business rule |
| [**listTemplateRules()**](EntityRuleApi.md#listTemplateRules) | **GET** /templates/{templateId}/rules | List the business rules of a template |
| [**toggleTemplateRule()**](EntityRuleApi.md#toggleTemplateRule) | **POST** /templates/{templateId}/rules/{id}/toggle | Enable or disable a business rule |
| [**updateTemplateRule()**](EntityRuleApi.md#updateTemplateRule) | **PUT** /templates/{templateId}/rules/{id} | Replace a business rule |


## `createTemplateRule()`

```php
createTemplateRule($templateId, $createEntityRuleRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\CreateTemplateRule201Response
```

Create a business rule on a template

Adds a rule of the form `when [conditions] then [constraints]` to a template. Rules are enforced synchronously in every entity write path (create, update, replace, batch, CSV import, MCP): when every `when` condition holds against the record's effective state, every `then` constraint must hold, otherwise the write is rejected with 422 and `errors` keyed by `attributes.<slug>`. An empty `when` makes the rule unconditional, which is how a required field is expressed (`then: [{attribute, is_not_empty}]`). Referenced attributes must belong to the template and must not be metrics; operators must fit the attribute's data type.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityRuleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or slug of the template
$createEntityRuleRequest = new \Omnismith\Sdk\Model\CreateEntityRuleRequest(); // \Omnismith\Sdk\Model\CreateEntityRuleRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->createTemplateRule($templateId, $createEntityRuleRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityRuleApi->createTemplateRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **createEntityRuleRequest** | [**\Omnismith\Sdk\Model\CreateEntityRuleRequest**](../Model/CreateEntityRuleRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\CreateTemplateRule201Response**](../Model/CreateTemplateRule201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteTemplateRule()`

```php
deleteTemplateRule($templateId, $id, $xOmnismithProjectId)
```

Delete a business rule

Permanently removes a rule from its template. Existing records are not re-validated.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityRuleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or slug of the template
$id = 01a09800-0000-7000-8000-000000000001; // string | Rule UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->deleteTemplateRule($templateId, $id, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling EntityRuleApi->deleteTemplateRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Rule UUID | |
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

## `getTemplateRule()`

```php
getTemplateRule($templateId, $id, $xOmnismithProjectId): \Omnismith\Sdk\Model\EntityRuleResponse
```

Get a business rule

Returns one rule of a template with its conditions and constraints.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityRuleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or slug of the template
$id = 01a09800-0000-7000-8000-000000000001; // string | Rule UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->getTemplateRule($templateId, $id, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityRuleApi->getTemplateRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Rule UUID | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\EntityRuleResponse**](../Model/EntityRuleResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplateRules()`

```php
listTemplateRules($templateId, $xOmnismithProjectId, $isEnabled): \Omnismith\Sdk\Model\ListTemplateRules200Response
```

List the business rules of a template

Returns every rule defined on a template in creation order, including disabled ones unless filtered. Read these before writing entities of the template: they are the invariants a create, update, replace, batch or import must satisfy, and a violation returns 422 with `errors` keyed by `attributes.<slug>`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityRuleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or slug of the template
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$isEnabled = True; // bool | Only enabled (`true`) or only disabled (`false`) rules

try {
    $result = $apiInstance->listTemplateRules($templateId, $xOmnismithProjectId, $isEnabled);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityRuleApi->listTemplateRules: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **isEnabled** | **bool**| Only enabled (&#x60;true&#x60;) or only disabled (&#x60;false&#x60;) rules | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ListTemplateRules200Response**](../Model/ListTemplateRules200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `toggleTemplateRule()`

```php
toggleTemplateRule($templateId, $id, $toggleEntityRuleRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\EntityRuleResponse
```

Enable or disable a business rule

Turns enforcement of a rule on or off without changing its definition. Disabled rules are stored but skipped by every write path.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityRuleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or slug of the template
$id = 01a09800-0000-7000-8000-000000000001; // string | Rule UUID
$toggleEntityRuleRequest = new \Omnismith\Sdk\Model\ToggleEntityRuleRequest(); // \Omnismith\Sdk\Model\ToggleEntityRuleRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->toggleTemplateRule($templateId, $id, $toggleEntityRuleRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityRuleApi->toggleTemplateRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Rule UUID | |
| **toggleEntityRuleRequest** | [**\Omnismith\Sdk\Model\ToggleEntityRuleRequest**](../Model/ToggleEntityRuleRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\EntityRuleResponse**](../Model/EntityRuleResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTemplateRule()`

```php
updateTemplateRule($templateId, $id, $updateEntityRuleRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\EntityRuleResponse
```

Replace a business rule

Replaces the name, message, conditions and constraints of a rule. The enabled flag is unchanged; use the toggle endpoint for that. The same validation as on create applies: attributes must belong to the template and must not be metrics, operators must fit the attribute's data type.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\EntityRuleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or slug of the template
$id = 01a09800-0000-7000-8000-000000000001; // string | Rule UUID
$updateEntityRuleRequest = new \Omnismith\Sdk\Model\UpdateEntityRuleRequest(); // \Omnismith\Sdk\Model\UpdateEntityRuleRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->updateTemplateRule($templateId, $id, $updateEntityRuleRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EntityRuleApi->updateTemplateRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Rule UUID | |
| **updateEntityRuleRequest** | [**\Omnismith\Sdk\Model\UpdateEntityRuleRequest**](../Model/UpdateEntityRuleRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\EntityRuleResponse**](../Model/EntityRuleResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
