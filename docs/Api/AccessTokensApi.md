# Omnismith\AccessTokensApi

AccessTokens

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAccessToken()**](AccessTokensApi.md#createAccessToken) | **POST** /access-tokens | Create an API access token |
| [**deleteAccessToken()**](AccessTokensApi.md#deleteAccessToken) | **DELETE** /access-tokens/{id} | Delete an API access token |
| [**listAccessTokens()**](AccessTokensApi.md#listAccessTokens) | **GET** /access-tokens | List API access tokens |


## `createAccessToken()`

```php
createAccessToken($create_access_token_request): \Omnismith\Model\CreateAccessToken201Response
```

Create an API access token

Creates a new API access token for the current user and project. The raw API key is returned once in the response and cannot be retrieved again.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_access_token_request = new \Omnismith\Model\CreateAccessTokenRequest(); // \Omnismith\Model\CreateAccessTokenRequest

try {
    $result = $apiInstance->createAccessToken($create_access_token_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccessTokensApi->createAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_access_token_request** | [**\Omnismith\Model\CreateAccessTokenRequest**](../Model/CreateAccessTokenRequest.md)|  | |

### Return type

[**\Omnismith\Model\CreateAccessToken201Response**](../Model/CreateAccessToken201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAccessToken()`

```php
deleteAccessToken($id)
```

Delete an API access token

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteAccessToken($id);
} catch (Exception $e) {
    echo 'Exception when calling AccessTokensApi->deleteAccessToken: ', $e->getMessage(), PHP_EOL;
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

## `listAccessTokens()`

```php
listAccessTokens(): \Omnismith\Model\ListAccessTokens200Response
```

List API access tokens

Returns all access tokens for the current user and project.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAccessTokens();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccessTokensApi->listAccessTokens: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\ListAccessTokens200Response**](../Model/ListAccessTokens200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
