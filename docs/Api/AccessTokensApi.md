# Omnismith\Sdk\AccessTokensApi

AccessTokens

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAccessToken()**](AccessTokensApi.md#createAccessToken) | **POST** /access-tokens | Create a programmatic API access token |
| [**deleteAccessToken()**](AccessTokensApi.md#deleteAccessToken) | **DELETE** /access-tokens/{id} | Delete an API access token |
| [**listAccessTokens()**](AccessTokensApi.md#listAccessTokens) | **GET** /access-tokens | List API access tokens |


## `createAccessToken()`

```php
createAccessToken($createAccessTokenRequest): \Omnismith\Sdk\Model\CreateAccessToken201Response
```

Create a programmatic API access token

Generates a new programmatic API access token prefixed with `omni_` (e.g. `omni_live_secret_key_...`) for the authenticated user within the active project context. The token inherits the user's current role permissions and scopes for authenticating automated API clients and scripts. The raw secret key is returned exactly once in the response and cannot be recovered later.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createAccessTokenRequest = new \Omnismith\Sdk\Model\CreateAccessTokenRequest(); // \Omnismith\Sdk\Model\CreateAccessTokenRequest

try {
    $result = $apiInstance->createAccessToken($createAccessTokenRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccessTokensApi->createAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createAccessTokenRequest** | [**\Omnismith\Sdk\Model\CreateAccessTokenRequest**](../Model/CreateAccessTokenRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateAccessToken201Response**](../Model/CreateAccessToken201Response.md)

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

Permanently revokes and removes a programmatic API access token by its unique identifier. Any future API request using the revoked secret key will immediately fail authentication with a 401 Unauthorized status.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AccessTokensApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0192a543-7f28-72b1-9b7e-97c997321034; // string | Unique UUIDv7 identifier of the access token to delete

try {
    $apiInstance->deleteAccessToken($id);
} catch (Exception $e) {
    echo 'Exception when calling AccessTokensApi->deleteAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUIDv7 identifier of the access token to delete | |

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

## `listAccessTokens()`

```php
listAccessTokens(): \Omnismith\Sdk\Model\ListAccessTokens200Response
```

List API access tokens

Retrieves all active and expired programmatic API access tokens created by the authenticated user for the active project context. Returns token metadata including unique ID, user-assigned label, creation date, expiration timestamp, and last used timestamp. Note: raw secret API keys are only displayed once upon generation and are never returned in list responses.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AccessTokensApi(
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

[**\Omnismith\Sdk\Model\ListAccessTokens200Response**](../Model/ListAccessTokens200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
