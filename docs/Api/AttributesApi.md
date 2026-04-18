# Omnismith\AttributesApi

Attributes

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAttribute()**](AttributesApi.md#createAttribute) | **POST** /attributes | Create a new attribute |
| [**createAttributeItem()**](AttributesApi.md#createAttributeItem) | **POST** /attributes/{id}/items | Add a list item to an attribute |
| [**deleteAttribute()**](AttributesApi.md#deleteAttribute) | **DELETE** /attributes/{id} | Delete an attribute |
| [**deleteAttributeItem()**](AttributesApi.md#deleteAttributeItem) | **DELETE** /attributes/{id}/items/{itemId} | Remove a list item from an attribute |
| [**deleteAttributeReferenceConfig()**](AttributesApi.md#deleteAttributeReferenceConfig) | **DELETE** /attributes/{id}/reference | Delete reference configuration for an attribute |
| [**getAttribute()**](AttributesApi.md#getAttribute) | **GET** /attributes/{id} | Get an attribute |
| [**getAttributeReferenceConfig()**](AttributesApi.md#getAttributeReferenceConfig) | **GET** /attributes/{id}/reference | Get reference configuration for an attribute |
| [**getProjectSchema()**](AttributesApi.md#getProjectSchema) | **GET** /discovery/project-schema | Get complete project schema |
| [**listAttributeItems()**](AttributesApi.md#listAttributeItems) | **GET** /attributes/{id}/items | List items of an attribute |
| [**listAttributes()**](AttributesApi.md#listAttributes) | **GET** /attributes | List attributes |
| [**setAttributeItems()**](AttributesApi.md#setAttributeItems) | **PUT** /attributes/{id}/items | Set list items for an attribute (replaces all existing items) |
| [**setAttributeReferenceConfig()**](AttributesApi.md#setAttributeReferenceConfig) | **PUT** /attributes/{id}/reference | Set or update reference configuration for an attribute |
| [**updateAttribute()**](AttributesApi.md#updateAttribute) | **PUT** /attributes/{id} | Update an attribute |
| [**updateAttributeItem()**](AttributesApi.md#updateAttributeItem) | **PUT** /attributes/{id}/items/{itemId} | Update a list item of an attribute |


## `createAttribute()`

```php
createAttribute($create_attribute_request): \Omnismith\Model\CreateAttributeItem201Response
```

Create a new attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_attribute_request = new \Omnismith\Model\CreateAttributeRequest(); // \Omnismith\Model\CreateAttributeRequest

try {
    $result = $apiInstance->createAttribute($create_attribute_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->createAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_attribute_request** | [**\Omnismith\Model\CreateAttributeRequest**](../Model/CreateAttributeRequest.md)|  | |

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

## `createAttributeItem()`

```php
createAttributeItem($id, $add_list_item_request): \Omnismith\Model\CreateAttributeItem201Response
```

Add a list item to an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID
$add_list_item_request = new \Omnismith\Model\AddListItemRequest(); // \Omnismith\Model\AddListItemRequest

try {
    $result = $apiInstance->createAttributeItem($id, $add_list_item_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->createAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |
| **add_list_item_request** | [**\Omnismith\Model\AddListItemRequest**](../Model/AddListItemRequest.md)|  | |

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

## `deleteAttribute()`

```php
deleteAttribute($id)
```

Delete an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteAttribute($id);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

## `deleteAttributeItem()`

```php
deleteAttributeItem($id, $item_id)
```

Remove a list item from an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID
$item_id = 'item_id_example'; // string | List Item ID

try {
    $apiInstance->deleteAttributeItem($id, $item_id);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |
| **item_id** | **string**| List Item ID | |

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

## `deleteAttributeReferenceConfig()`

```php
deleteAttributeReferenceConfig($id)
```

Delete reference configuration for an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID

try {
    $apiInstance->deleteAttributeReferenceConfig($id);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |

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

## `getAttribute()`

```php
getAttribute($id): \Omnismith\Model\AttributeResponse
```

Get an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

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
| **id** | **string**|  | |

### Return type

[**\Omnismith\Model\AttributeResponse**](../Model/AttributeResponse.md)

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
getAttributeReferenceConfig($id): \Omnismith\Model\ReferenceConfigResponse
```

Get reference configuration for an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID

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
| **id** | **string**| Attribute ID | |

### Return type

[**\Omnismith\Model\ReferenceConfigResponse**](../Model/ReferenceConfigResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProjectSchema()`

```php
getProjectSchema(): \Omnismith\Model\ProjectSchemaResponse
```

Get complete project schema

Returns all attributes, templates, list items, and reference configs in a single response

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getProjectSchema();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->getProjectSchema: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\ProjectSchemaResponse**](../Model/ProjectSchemaResponse.md)

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
listAttributeItems($id): \Omnismith\Model\ListAttributeItems200Response
```

List items of an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID

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
| **id** | **string**| Attribute ID | |

### Return type

[**\Omnismith\Model\ListAttributeItems200Response**](../Model/ListAttributeItems200Response.md)

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
listAttributes(): \Omnismith\Model\ListAttributes200Response
```

List attributes

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
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

[**\Omnismith\Model\ListAttributes200Response**](../Model/ListAttributes200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `setAttributeItems()`

```php
setAttributeItems($id, $set_list_items_request)
```

Set list items for an attribute (replaces all existing items)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID
$set_list_items_request = new \Omnismith\Model\SetListItemsRequest(); // \Omnismith\Model\SetListItemsRequest

try {
    $apiInstance->setAttributeItems($id, $set_list_items_request);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->setAttributeItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |
| **set_list_items_request** | [**\Omnismith\Model\SetListItemsRequest**](../Model/SetListItemsRequest.md)|  | |

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
setAttributeReferenceConfig($id, $set_reference_config_request)
```

Set or update reference configuration for an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID
$set_reference_config_request = new \Omnismith\Model\SetReferenceConfigRequest(); // \Omnismith\Model\SetReferenceConfigRequest

try {
    $apiInstance->setAttributeReferenceConfig($id, $set_reference_config_request);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->setAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |
| **set_reference_config_request** | [**\Omnismith\Model\SetReferenceConfigRequest**](../Model/SetReferenceConfigRequest.md)|  | |

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
updateAttribute($id, $update_attribute_request)
```

Update an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_attribute_request = new \Omnismith\Model\UpdateAttributeRequest(); // \Omnismith\Model\UpdateAttributeRequest

try {
    $apiInstance->updateAttribute($id, $update_attribute_request);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->updateAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_attribute_request** | [**\Omnismith\Model\UpdateAttributeRequest**](../Model/UpdateAttributeRequest.md)|  | |

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
updateAttributeItem($id, $item_id, $update_list_item_request)
```

Update a list item of an attribute

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AttributesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Attribute ID
$item_id = 'item_id_example'; // string | List Item ID
$update_list_item_request = new \Omnismith\Model\UpdateListItemRequest(); // \Omnismith\Model\UpdateListItemRequest

try {
    $apiInstance->updateAttributeItem($id, $item_id, $update_list_item_request);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->updateAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |
| **item_id** | **string**| List Item ID | |
| **update_list_item_request** | [**\Omnismith\Model\UpdateListItemRequest**](../Model/UpdateListItemRequest.md)|  | |

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
