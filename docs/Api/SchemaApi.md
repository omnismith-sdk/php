# Omnismith\Sdk\SchemaApi

Schema

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getProjectSchema()**](SchemaApi.md#getProjectSchema) | **GET** /discovery/project-schema | Get complete project schema |


## `getProjectSchema()`

```php
getProjectSchema(): \Omnismith\Sdk\Model\ProjectSchemaResponse
```

Get complete project schema

Returns all attributes, templates, list items, and reference configs in a single response

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\SchemaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getProjectSchema();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SchemaApi->getProjectSchema: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ProjectSchemaResponse**](../Model/ProjectSchemaResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
