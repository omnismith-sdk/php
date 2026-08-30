# Omnismith\Sdk\MarketplaceApi

Marketplace

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteMarketplaceBlueprint()**](MarketplaceApi.md#deleteMarketplaceBlueprint) | **DELETE** /marketplace/blueprints/{id} | Delete a marketplace blueprint |
| [**getMarketplaceBlueprint()**](MarketplaceApi.md#getMarketplaceBlueprint) | **GET** /marketplace/blueprints/{id} | Get marketplace blueprint details |
| [**installMarketplaceBlueprint()**](MarketplaceApi.md#installMarketplaceBlueprint) | **POST** /marketplace/blueprints/{id}/install | Install a marketplace blueprint into a project |
| [**listMarketplaceKeywords()**](MarketplaceApi.md#listMarketplaceKeywords) | **GET** /marketplace/keywords | List marketplace keywords |
| [**publishMarketplaceBlueprint()**](MarketplaceApi.md#publishMarketplaceBlueprint) | **POST** /marketplace/blueprints | Publish or update a marketplace blueprint |
| [**searchMarketplaceBlueprints()**](MarketplaceApi.md#searchMarketplaceBlueprints) | **GET** /marketplace/blueprints | Search marketplace blueprints |


## `deleteMarketplaceBlueprint()`

```php
deleteMarketplaceBlueprint($id)
```

Delete a marketplace blueprint

Permanently removes a published blueprint from the marketplace catalog. Only the author who published the blueprint or a system administrator has permission to delete it.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60003; // string | Unique blueprint UUID to delete

try {
    $apiInstance->deleteMarketplaceBlueprint($id);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->deleteMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique blueprint UUID to delete | |

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
getMarketplaceBlueprint($id): \Omnismith\Sdk\Model\GetMarketplaceBlueprint200Response
```

Get marketplace blueprint details

Retrieves complete information for a specific marketplace blueprint by its UUID. Returns full blueprint metadata, publisher details, popularity metrics, and packaged blueprint schema definition containing template schemas, attribute configurations, and optional demo entities.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60003; // string | Unique marketplace blueprint UUID

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
| **id** | **string**| Unique marketplace blueprint UUID | |

### Return type

[**\Omnismith\Sdk\Model\GetMarketplaceBlueprint200Response**](../Model/GetMarketplaceBlueprint200Response.md)

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
installMarketplaceBlueprint($id, $installMarketplaceBlueprintRequest)
```

Install a marketplace blueprint into a project

Installs a marketplace blueprint into the specified project context. Provisions all packaged templates, attributes, and relationships defined in the blueprint schema, and optionally populates sample demo entities. Automatically increments the installation count for the blueprint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60003; // string | Unique UUID of the blueprint to install
$installMarketplaceBlueprintRequest = new \Omnismith\Sdk\Model\InstallMarketplaceBlueprintRequest(); // \Omnismith\Sdk\Model\InstallMarketplaceBlueprintRequest

try {
    $apiInstance->installMarketplaceBlueprint($id, $installMarketplaceBlueprintRequest);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->installMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the blueprint to install | |
| **installMarketplaceBlueprintRequest** | [**\Omnismith\Sdk\Model\InstallMarketplaceBlueprintRequest**](../Model/InstallMarketplaceBlueprintRequest.md)|  | |

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
listMarketplaceKeywords(): \Omnismith\Sdk\Model\ListMarketplaceKeywords200Response
```

List marketplace keywords

Retrieves all distinct categorization keywords and tags associated with published blueprints along with their total occurrence count, ordered by popularity descending. Useful for populating discovery tags, filters, and keyword clouds.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\MarketplaceApi(
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

[**\Omnismith\Sdk\Model\ListMarketplaceKeywords200Response**](../Model/ListMarketplaceKeywords200Response.md)

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
publishMarketplaceBlueprint($publishMarketplaceBlueprintRequest): \Omnismith\Sdk\Model\GetMarketplaceBlueprint200Response
```

Publish or update a marketplace blueprint

Publishes a new blueprint to the public marketplace or updates an existing blueprint owned by the authenticated user. Snapshots selected templates, attributes, and optional sample entities into an exportable blueprint package with title, description, and searchable keywords.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$publishMarketplaceBlueprintRequest = new \Omnismith\Sdk\Model\PublishMarketplaceBlueprintRequest(); // \Omnismith\Sdk\Model\PublishMarketplaceBlueprintRequest

try {
    $result = $apiInstance->publishMarketplaceBlueprint($publishMarketplaceBlueprintRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->publishMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **publishMarketplaceBlueprintRequest** | [**\Omnismith\Sdk\Model\PublishMarketplaceBlueprintRequest**](../Model/PublishMarketplaceBlueprintRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\GetMarketplaceBlueprint200Response**](../Model/GetMarketplaceBlueprint200Response.md)

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
searchMarketplaceBlueprints($search, $keywords, $limit, $offset, $sortBy, $sortDirection, $featured): \Omnismith\Sdk\Model\SearchMarketplaceBlueprints200Response
```

Search marketplace blueprints

Searches and lists public blueprints available in the marketplace catalog. Blueprints package reusable template schemas, attribute definitions, and sample data that users can install directly into their projects. Supports full-text search across titles and descriptions, keyword tag filtering, filtering by featured status, and sorting by creation date, install counts, or title.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$search = crm pipeline; // string | Free-text search filter across blueprint title and description
$keywords = crm,sales,leads; // string | Comma-separated keywords or tags to filter blueprints
$limit = 20; // int | Number of blueprint records to return per page (max 100)
$offset = 0; // int | Number of blueprint records to skip for pagination
$sortBy = installs; // string | Field to sort blueprint results by
$sortDirection = desc; // string | Sort direction order (ascending or descending)
$featured = true; // bool | Filter to return only curated and featured marketplace blueprints

try {
    $result = $apiInstance->searchMarketplaceBlueprints($search, $keywords, $limit, $offset, $sortBy, $sortDirection, $featured);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->searchMarketplaceBlueprints: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **search** | **string**| Free-text search filter across blueprint title and description | [optional] |
| **keywords** | **string**| Comma-separated keywords or tags to filter blueprints | [optional] |
| **limit** | **int**| Number of blueprint records to return per page (max 100) | [optional] [default to 20] |
| **offset** | **int**| Number of blueprint records to skip for pagination | [optional] [default to 0] |
| **sortBy** | **string**| Field to sort blueprint results by | [optional] [default to &#39;created_at&#39;] |
| **sortDirection** | **string**| Sort direction order (ascending or descending) | [optional] [default to &#39;desc&#39;] |
| **featured** | **bool**| Filter to return only curated and featured marketplace blueprints | [optional] |

### Return type

[**\Omnismith\Sdk\Model\SearchMarketplaceBlueprints200Response**](../Model/SearchMarketplaceBlueprints200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
