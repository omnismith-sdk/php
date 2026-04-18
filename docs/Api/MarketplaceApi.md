# Omnismith\MarketplaceApi

Marketplace

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteMarketplaceBlueprint()**](MarketplaceApi.md#deleteMarketplaceBlueprint) | **DELETE** /marketplace/blueprints/{id} | Delete a marketplace blueprint |
| [**getMarketplaceBlueprint()**](MarketplaceApi.md#getMarketplaceBlueprint) | **GET** /marketplace/blueprints/{id} | Get marketplace blueprint details |
| [**installMarketplaceBlueprint()**](MarketplaceApi.md#installMarketplaceBlueprint) | **POST** /marketplace/blueprints/{id}/install | Install a marketplace blueprint into a project |
| [**listMarketplaceKeywords()**](MarketplaceApi.md#listMarketplaceKeywords) | **GET** /marketplace/keywords | List all marketplace keywords with blueprint counts |
| [**publishMarketplaceBlueprint()**](MarketplaceApi.md#publishMarketplaceBlueprint) | **POST** /marketplace/blueprints | Publish or update a marketplace blueprint |
| [**searchMarketplaceBlueprints()**](MarketplaceApi.md#searchMarketplaceBlueprints) | **GET** /marketplace/blueprints | Search marketplace blueprints |


## `deleteMarketplaceBlueprint()`

```php
deleteMarketplaceBlueprint($id)
```

Delete a marketplace blueprint

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Blueprint ID

try {
    $apiInstance->deleteMarketplaceBlueprint($id);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->deleteMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Blueprint ID | |

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

## `getMarketplaceBlueprint()`

```php
getMarketplaceBlueprint($id): \Omnismith\Model\GetMarketplaceBlueprint200Response
```

Get marketplace blueprint details

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | Blueprint ID

try {
    $result = $apiInstance->getMarketplaceBlueprint($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Blueprint ID | |

### Return type

[**\Omnismith\Model\GetMarketplaceBlueprint200Response**](../Model/GetMarketplaceBlueprint200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `installMarketplaceBlueprint()`

```php
installMarketplaceBlueprint($id, $install_marketplace_blueprint_request)
```

Install a marketplace blueprint into a project

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Blueprint ID
$install_marketplace_blueprint_request = new \Omnismith\Model\InstallMarketplaceBlueprintRequest(); // \Omnismith\Model\InstallMarketplaceBlueprintRequest

try {
    $apiInstance->installMarketplaceBlueprint($id, $install_marketplace_blueprint_request);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->installMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Blueprint ID | |
| **install_marketplace_blueprint_request** | [**\Omnismith\Model\InstallMarketplaceBlueprintRequest**](../Model/InstallMarketplaceBlueprintRequest.md)|  | |

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

## `listMarketplaceKeywords()`

```php
listMarketplaceKeywords(): \Omnismith\Model\ListMarketplaceKeywords200Response
```

List all marketplace keywords with blueprint counts

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->listMarketplaceKeywords();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->listMarketplaceKeywords: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\ListMarketplaceKeywords200Response**](../Model/ListMarketplaceKeywords200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `publishMarketplaceBlueprint()`

```php
publishMarketplaceBlueprint($publish_marketplace_blueprint_request): \Omnismith\Model\GetMarketplaceBlueprint200Response
```

Publish or update a marketplace blueprint

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$publish_marketplace_blueprint_request = new \Omnismith\Model\PublishMarketplaceBlueprintRequest(); // \Omnismith\Model\PublishMarketplaceBlueprintRequest

try {
    $result = $apiInstance->publishMarketplaceBlueprint($publish_marketplace_blueprint_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->publishMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **publish_marketplace_blueprint_request** | [**\Omnismith\Model\PublishMarketplaceBlueprintRequest**](../Model/PublishMarketplaceBlueprintRequest.md)|  | |

### Return type

[**\Omnismith\Model\GetMarketplaceBlueprint200Response**](../Model/GetMarketplaceBlueprint200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchMarketplaceBlueprints()`

```php
searchMarketplaceBlueprints($search, $keywords, $limit, $offset, $sort_by, $sort_direction, $featured): \Omnismith\Model\SearchMarketplaceBlueprints200Response
```

Search marketplace blueprints

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$search = 'search_example'; // string | Free-text search on title and description
$keywords = 'keywords_example'; // string | Comma-separated keywords to filter by
$limit = 20; // int | Number of results per page
$offset = 0; // int | Pagination offset
$sort_by = 'created_at'; // string | Sort field
$sort_direction = 'desc'; // string | Sort direction
$featured = True; // bool | Filter by featured status

try {
    $result = $apiInstance->searchMarketplaceBlueprints($search, $keywords, $limit, $offset, $sort_by, $sort_direction, $featured);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->searchMarketplaceBlueprints: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **search** | **string**| Free-text search on title and description | [optional] |
| **keywords** | **string**| Comma-separated keywords to filter by | [optional] |
| **limit** | **int**| Number of results per page | [optional] [default to 20] |
| **offset** | **int**| Pagination offset | [optional] [default to 0] |
| **sort_by** | **string**| Sort field | [optional] [default to &#39;created_at&#39;] |
| **sort_direction** | **string**| Sort direction | [optional] [default to &#39;desc&#39;] |
| **featured** | **bool**| Filter by featured status | [optional] |

### Return type

[**\Omnismith\Model\SearchMarketplaceBlueprints200Response**](../Model/SearchMarketplaceBlueprints200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
