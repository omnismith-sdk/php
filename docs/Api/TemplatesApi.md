# Omnismith\Sdk\TemplatesApi

Templates

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTemplate()**](TemplatesApi.md#createTemplate) | **POST** /templates | Create a new template |
| [**deleteTemplate()**](TemplatesApi.md#deleteTemplate) | **DELETE** /templates/{id} | Delete a template |
| [**getTemplate()**](TemplatesApi.md#getTemplate) | **GET** /templates/{id} | Get a template by ID or slug |
| [**listTemplateEntityCounts()**](TemplatesApi.md#listTemplateEntityCounts) | **GET** /templates/entity-counts | List entity counts per template |
| [**listTemplates()**](TemplatesApi.md#listTemplates) | **GET** /templates | List all templates |
| [**patchTemplate()**](TemplatesApi.md#patchTemplate) | **PATCH** /templates/{id} | Patch a template (granular partial update) |
| [**updateTemplate()**](TemplatesApi.md#updateTemplate) | **PUT** /templates/{id} | Update a template (full replacement) |


## `createTemplate()`

```php
createTemplate($createTemplateRequest): \Omnismith\Sdk\Model\CreateTemplate201Response
```

Create a new template

Creates a new dynamic schema template (content type) in the project. Accepts template name, optional description, category, unique slug, attribute bindings, and UI layout groups. Attribute bindings can be defined using structured `attributes` (with optional `default_value` validated against attribute kind/data type) or flat `attribute_ids` / `attribute_slugs`. Visual layout groups organize attributes into 1- or 2-column sections with optional icons. Creating templates is subject to tier quota limits.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createTemplateRequest = new \Omnismith\Sdk\Model\CreateTemplateRequest(); // \Omnismith\Sdk\Model\CreateTemplateRequest

try {
    $result = $apiInstance->createTemplate($createTemplateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->createTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createTemplateRequest** | [**\Omnismith\Sdk\Model\CreateTemplateRequest**](../Model/CreateTemplateRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateTemplate201Response**](../Model/CreateTemplate201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteTemplate()`

```php
deleteTemplate($id)
```

Delete a template

Soft-deletes a template definition by UUID or slug. Soft-deleted templates are hidden from normal listings, and entity creation under deleted templates is prevented.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to delete

try {
    $apiInstance->deleteTemplate($id);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->deleteTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to delete | |

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

## `getTemplate()`

```php
getTemplate($id): \Omnismith\Sdk\Model\TemplateResponse
```

Get a template by ID or slug

Retrieves complete template schema details by UUID or unique slug, including ordered attribute bindings, default values per attribute, and visual UI layout groups. Automatically filters out any restricted attributes the caller is not permitted to view.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to retrieve

try {
    $result = $apiInstance->getTemplate($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->getTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to retrieve | |

### Return type

[**\Omnismith\Sdk\Model\TemplateResponse**](../Model/TemplateResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplateEntityCounts()`

```php
listTemplateEntityCounts(): \Omnismith\Sdk\Model\ListTemplateEntityCounts200Response
```

List entity counts per template

Returns total entity record counts grouped by template UUID for all accessible templates in the current project context. Efficiently calculates counts and honors role-based resource access restrictions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listTemplateEntityCounts();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->listTemplateEntityCounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListTemplateEntityCounts200Response**](../Model/ListTemplateEntityCounts200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplates()`

```php
listTemplates(): \Omnismith\Sdk\Model\ListTemplates200Response
```

List all templates

Retrieves all dynamic schema templates defined within the active project context. Templates represent content types grouping reusable attributes, establishing per-template default values, and organizing fields into visual layout groups for the UI workbench and entity forms.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listTemplates();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->listTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListTemplates200Response**](../Model/ListTemplates200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchTemplate()`

```php
patchTemplate($id, $patchTemplateRequest)
```

Patch a template (granular partial update)

Applies partial modifications to an existing template by UUID or slug without overwriting omitted fields. Allows modifying name, description, category, slug, attribute associations (with validated default values), or visual layout groups independently. Safely merges and preserves any restricted attributes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to patch
$patchTemplateRequest = new \Omnismith\Sdk\Model\PatchTemplateRequest(); // \Omnismith\Sdk\Model\PatchTemplateRequest

try {
    $apiInstance->patchTemplate($id, $patchTemplateRequest);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->patchTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to patch | |
| **patchTemplateRequest** | [**\Omnismith\Sdk\Model\PatchTemplateRequest**](../Model/PatchTemplateRequest.md)|  | |

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

## `updateTemplate()`

```php
updateTemplate($id, $updateTemplateRequest)
```

Update a template (full replacement)

Performs a full update of an existing template definition by UUID or slug. Replaces name, description, category, slug, attribute associations (with validated per-attribute default values), and UI layout groups. If the caller lacks permissions to certain restricted attributes, those restricted attributes are automatically preserved in the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to update
$updateTemplateRequest = new \Omnismith\Sdk\Model\UpdateTemplateRequest(); // \Omnismith\Sdk\Model\UpdateTemplateRequest

try {
    $apiInstance->updateTemplate($id, $updateTemplateRequest);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->updateTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to update | |
| **updateTemplateRequest** | [**\Omnismith\Sdk\Model\UpdateTemplateRequest**](../Model/UpdateTemplateRequest.md)|  | |

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
