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
| [**getAttribute()**](AttributesApi.md#getAttribute) | **GET** /attributes/{id} | Get an attribute |
| [**getAttributeReferenceConfig()**](AttributesApi.md#getAttributeReferenceConfig) | **GET** /attributes/{id}/reference | Get reference configuration for an attribute |
| [**listAttributeItems()**](AttributesApi.md#listAttributeItems) | **GET** /attributes/{id}/items | List items of an attribute |
| [**listAttributes()**](AttributesApi.md#listAttributes) | **GET** /attributes | List attributes |
| [**setAttributeItems()**](AttributesApi.md#setAttributeItems) | **PUT** /attributes/{id}/items | Set list items for an attribute (replaces all existing items) |
| [**setAttributeReferenceConfig()**](AttributesApi.md#setAttributeReferenceConfig) | **PUT** /attributes/{id}/reference | Set or update reference configuration for an attribute |
| [**updateAttribute()**](AttributesApi.md#updateAttribute) | **PUT** /attributes/{id} | Update an attribute |
| [**updateAttributeItem()**](AttributesApi.md#updateAttributeItem) | **PUT** /attributes/{id}/items/{itemId} | Update a list item of an attribute |


## `createAttribute()`

```php
createAttribute($createAttributeRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Create a new attribute

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

[**\Omnismith\Sdk\Model\CreateAttributeItem201Response**](../Model/CreateAttributeItem201Response.md)

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
$id = 'id_example'; // string | Attribute ID
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
| **id** | **string**| Attribute ID | |
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
deleteAttributeItem($id, $itemId)
```

Remove a list item from an attribute

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
$id = 'id_example'; // string | Attribute ID
$itemId = 'itemId_example'; // string | List Item ID

try {
    $apiInstance->deleteAttributeItem($id, $itemId);
} catch (Exception $e) {
    echo 'Exception when calling AttributesApi->deleteAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Attribute ID | |
| **itemId** | **string**| List Item ID | |

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
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AttributesApi(
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
getAttribute($id): \Omnismith\Sdk\Model\AttributeResponse
```

Get an attribute

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

List attributes

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

## `setAttributeItems()`

```php
setAttributeItems($id, $setListItemsRequest)
```

Set list items for an attribute (replaces all existing items)

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
$id = 'id_example'; // string | Attribute ID
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
| **id** | **string**| Attribute ID | |
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
$id = 'id_example'; // string | Attribute ID
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
| **id** | **string**| Attribute ID | |
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

Update an attribute

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
$id = 'id_example'; // string
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
| **id** | **string**|  | |
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
$id = 'id_example'; // string | Attribute ID
$itemId = 'itemId_example'; // string | List Item ID
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
| **id** | **string**| Attribute ID | |
| **itemId** | **string**| List Item ID | |
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
