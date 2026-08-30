# Omnismith\Sdk\AttributesApi

Attributes

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAttribute()**](AttributesApi.md#createAttribute) | **POST** /attributes | Create a new attribute |
| [**createAttributeItem()**](AttributesApi.md#createAttributeItem) | **POST** /attributes/{id}/items | Add a list item to an attribute |
| [**deleteAttribute()**](AttributesApi.md#deleteAttribute) | **DELETE** /attributes/{id} | Delete an attribute |
| [**deleteAttributeItem()**](AttributesApi.md#deleteAttributeItem) | **DELETE** /attributes/{id}/items/{itemId} | Remove a list item from an attribute |
| [**deleteAttributeReferenceConfig()**](AttributesApi.md#deleteAttributeReferenceConfig) | **DELETE** /attributes/{id}/reference | Delete reference configuration for an attribute |
| [**getAttribute()**](AttributesApi.md#getAttribute) | **GET** /attributes/{id} | Get an attribute by ID |
| [**getAttributeReferenceConfig()**](AttributesApi.md#getAttributeReferenceConfig) | **GET** /attributes/{id}/reference | Get reference configuration for an attribute |
| [**listAttributeItems()**](AttributesApi.md#listAttributeItems) | **GET** /attributes/{id}/items | List items of an attribute |
| [**listAttributes()**](AttributesApi.md#listAttributes) | **GET** /attributes | List all attributes |
| [**patchAttribute()**](AttributesApi.md#patchAttribute) | **PATCH** /attributes/{id} | Patch an attribute (granular partial update) |
| [**setAttributeItems()**](AttributesApi.md#setAttributeItems) | **PUT** /attributes/{id}/items | Set list items for an attribute (replaces all existing items) |
| [**setAttributeReferenceConfig()**](AttributesApi.md#setAttributeReferenceConfig) | **PUT** /attributes/{id}/reference | Set or update reference configuration for an attribute |
| [**updateAttribute()**](AttributesApi.md#updateAttribute) | **PUT** /attributes/{id} | Update an attribute (full replacement) |
| [**updateAttributeItem()**](AttributesApi.md#updateAttributeItem) | **PUT** /attributes/{id}/items/{itemId} | Update a list item of an attribute |


## `createAttribute()`

```php
createAttribute($createAttributeRequest): \Omnismith\Sdk\Model\CreateAttribute201Response
```

Create a new attribute

Defines a new attribute in the project schema. Attributes can be of kind Dimension (0), Metric (1), List (2), or Reference (3). Specify the storage data type (String: 0, Number: 1, Boolean: 2, Datetime: 3, Date: 4, File: 5, Image: 6, Markdown: 7), name, optional project-unique slug (auto-generated from name if omitted), optional template associations, and an optional reference_config if kind is Reference (3). Subject to project tier quota constraints.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createAttributeRequest = new \Omnismith\Sdk\Model\CreateAttributeRequest(); // \Omnismith\Sdk\Model\CreateAttributeRequest

try {
    $result = $apiInstance->createAttribute($createAttributeRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->createAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createAttributeRequest** | [**\Omnismith\Sdk\Model\CreateAttributeRequest**](../Model/CreateAttributeRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateAttribute201Response**](../Model/CreateAttribute201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAttributeItem()`

```php
createAttributeItem($id, $addListItemRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Add a list item to an attribute

Appends a single selectable choice option item to a List-type (attribute_type = 2) attribute. Returns the generated or assigned UUID of the newly created list item.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the List-type attribute
$addListItemRequest = new \Omnismith\Sdk\Model\AddListItemRequest(); // \Omnismith\Sdk\Model\AddListItemRequest

try {
    $result = $apiInstance->createAttributeItem($id, $addListItemRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->createAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the List-type attribute | |
| **addListItemRequest** | [**\Omnismith\Sdk\Model\AddListItemRequest**](../Model/AddListItemRequest.md)|  | |

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

## `deleteAttribute()`

```php
deleteAttribute($id)
```

Delete an attribute

Soft-deletes an attribute from the project schema. Soft-deleted attributes are removed from active template projections and future queries, while existing historical dimension and telemetry records remain preserved for audit integrity.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to delete

try {
    $apiInstance->deleteAttribute($id);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to delete | |

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

## `deleteAttributeItem()`

```php
deleteAttributeItem($id, $itemId)
```

Remove a list item from an attribute

Permanently deletes a specific selectable option item from a List-type (attribute_type = 2) attribute. Validates that the list item exists and belongs to the specified attribute before deletion.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the parent List attribute
$itemId = 019a6b2c-8c3a-7c2e-8b3f-6c8a1a2b3c4d; // string | UUID of the list item to delete

try {
    $apiInstance->deleteAttributeItem($id, $itemId);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the parent List attribute | |
| **itemId** | **string**| UUID of the list item to delete | |

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

## `deleteAttributeReferenceConfig()`

```php
deleteAttributeReferenceConfig($id)
```

Delete reference configuration for an attribute

Removes the foreign entity reference configuration mapping from a Reference-type (attribute_type = 3) attribute.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the Reference attribute

try {
    $apiInstance->deleteAttributeReferenceConfig($id);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the Reference attribute | |

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

## `getAttribute()`

```php
getAttribute($id): \Omnismith\Sdk\Model\AttributeResponse
```

Get an attribute by ID

Retrieves complete attribute metadata by its UUID, including kind (Dimension: 0, Metric: 1, List: 2, Reference: 3), storage data type, assigned template IDs, creation timestamps, and reference configuration if applicable.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to fetch

try {
    $result = $apiInstance->getAttribute($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->getAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to fetch | |

### Return type

[**\Omnismith\Sdk\Model\AttributeResponse**](../Model/AttributeResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAttributeReferenceConfig()`

```php
getAttributeReferenceConfig($id): \Omnismith\Sdk\Model\ReferenceConfigResponse
```

Get reference configuration for an attribute

Retrieves the relational reference target configuration for a Reference-type (attribute_type = 3) attribute. Returns the target template UUID and target display attribute UUID used for entity reference pointer resolution.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the Reference attribute

try {
    $result = $apiInstance->getAttributeReferenceConfig($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->getAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the Reference attribute | |

### Return type

[**\Omnismith\Sdk\Model\ReferenceConfigResponse**](../Model/ReferenceConfigResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAttributeItems()`

```php
listAttributeItems($id): \Omnismith\Sdk\Model\ListAttributeItems200Response
```

List items of an attribute

Retrieves all selectable choice option items for a List-type (attribute_type = 2) attribute in ascending sort order. Each item contains its UUID, parent attribute ID, string value, and sort rank.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the List-type attribute

try {
    $result = $apiInstance->listAttributeItems($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->listAttributeItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the List-type attribute | |

### Return type

[**\Omnismith\Sdk\Model\ListAttributeItems200Response**](../Model/ListAttributeItems200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAttributes()`

```php
listAttributes(): \Omnismith\Sdk\Model\ListAttributes200Response
```

List all attributes

Retrieves all schema attributes defined in the active project. Attributes represent the core schema building blocks across 4 kinds: Dimension (0), Metric (1), List (2), and Reference (3). Each attribute defines its storage data type (String: 0, Number: 1, Boolean: 2, Datetime: 3, Date: 4, File: 5, Image: 6, Markdown: 7), unique slug, optional description, associated templates, and reference configurations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAttributes();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->listAttributes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListAttributes200Response**](../Model/ListAttributes200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchAttribute()`

```php
patchAttribute($id, $patchAttributeRequest)
```

Patch an attribute (granular partial update)

Applies partial modifications to an existing attribute without overwriting omitted fields. Allows independently changing name, description, slug, template associations, reference configuration, or transitioning data type. Lossless data type transition rules apply when updating data_type (Dimension only: Number(1)->String(0), Boolean(2)->String(0), Date(4)<->Datetime(3), Date(4)/Datetime(3)->String(0), String(0)<->Markdown(7)). Template associations merge and preserve restricted templates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to patch
$patchAttributeRequest = new \Omnismith\Sdk\Model\PatchAttributeRequest(); // \Omnismith\Sdk\Model\PatchAttributeRequest

try {
    $apiInstance->patchAttribute($id, $patchAttributeRequest);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->patchAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to patch | |
| **patchAttributeRequest** | [**\Omnismith\Sdk\Model\PatchAttributeRequest**](../Model/PatchAttributeRequest.md)|  | |

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

## `setAttributeItems()`

```php
setAttributeItems($id, $setListItemsRequest)
```

Set list items for an attribute (replaces all existing items)

Atomically replaces all selectable option items for a List-type (attribute_type = 2) attribute. Existing list items for this attribute are removed and replaced with the provided array of items (with values, sort orders, and optional custom UUIDs). Returns HTTP 400 if the target attribute is not of List kind.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the List-type attribute
$setListItemsRequest = new \Omnismith\Sdk\Model\SetListItemsRequest(); // \Omnismith\Sdk\Model\SetListItemsRequest

try {
    $apiInstance->setAttributeItems($id, $setListItemsRequest);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->setAttributeItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the List-type attribute | |
| **setListItemsRequest** | [**\Omnismith\Sdk\Model\SetListItemsRequest**](../Model/SetListItemsRequest.md)|  | |

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

## `setAttributeReferenceConfig()`

```php
setAttributeReferenceConfig($id, $setReferenceConfigRequest)
```

Set or update reference configuration for an attribute

Sets or updates the target template and display attribute for a Reference-type (attribute_type = 3) attribute. Enables relational linking and foreign entity display label resolution. Returns HTTP 400 if the target attribute is not of Reference kind.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the Reference attribute
$setReferenceConfigRequest = new \Omnismith\Sdk\Model\SetReferenceConfigRequest(); // \Omnismith\Sdk\Model\SetReferenceConfigRequest

try {
    $apiInstance->setAttributeReferenceConfig($id, $setReferenceConfigRequest);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->setAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the Reference attribute | |
| **setReferenceConfigRequest** | [**\Omnismith\Sdk\Model\SetReferenceConfigRequest**](../Model/SetReferenceConfigRequest.md)|  | |

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

## `updateAttribute()`

```php
updateAttribute($id, $updateAttributeRequest)
```

Update an attribute (full replacement)

Performs a full update of an existing attribute definition. Supports updating name, description, slug, template associations, reference configuration, and lossless data type transitions. Data type transitions are permitted only for Dimension (0) attributes and must follow lossless compatibility: Number(1) -> String(0), Boolean(2) -> String(0), Date(4) <-> Datetime(3), Date(4)/Datetime(3) -> String(0), and String(0) <-> Markdown(7). Non-lossless transitions or transitions on non-dimension attributes will return HTTP 422. Template associations preserve restricted templates the caller cannot see.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to update
$updateAttributeRequest = new \Omnismith\Sdk\Model\UpdateAttributeRequest(); // \Omnismith\Sdk\Model\UpdateAttributeRequest

try {
    $apiInstance->updateAttribute($id, $updateAttributeRequest);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->updateAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to update | |
| **updateAttributeRequest** | [**\Omnismith\Sdk\Model\UpdateAttributeRequest**](../Model/UpdateAttributeRequest.md)|  | |

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

## `updateAttributeItem()`

```php
updateAttributeItem($id, $itemId, $updateListItemRequest)
```

Update a list item of an attribute

Updates the display value and/or sort order of an existing list item belonging to a List-type (attribute_type = 2) attribute. Validates that the list item exists and belongs to the specified attribute.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the parent List attribute
$itemId = 019a6b2c-8c3a-7c2e-8b3f-6c8a1a2b3c4d; // string | UUID of the list item to update
$updateListItemRequest = new \Omnismith\Sdk\Model\UpdateListItemRequest(); // \Omnismith\Sdk\Model\UpdateListItemRequest

try {
    $apiInstance->updateAttributeItem($id, $itemId, $updateListItemRequest);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->updateAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the parent List attribute | |
| **itemId** | **string**| UUID of the list item to update | |
| **updateListItemRequest** | [**\Omnismith\Sdk\Model\UpdateListItemRequest**](../Model/UpdateListItemRequest.md)|  | |

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
