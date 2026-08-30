# Omnismith\Sdk\OAuthApi

OAuth

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**approveOAuthAuthorization()**](OAuthApi.md#approveOAuthAuthorization) | **POST** /oauth/authorize/approve | Approve OAuth Authorization Consent |
| [**exchangeOAuthToken()**](OAuthApi.md#exchangeOAuthToken) | **POST** /oauth/token | Exchange OAuth 2.0 Token |
| [**getJwks()**](OAuthApi.md#getJwks) | **GET** /.well-known/jwks.json | Get JSON Web Key Set |
| [**getOAuthAuthorizeInfo()**](OAuthApi.md#getOAuthAuthorizeInfo) | **GET** /oauth/authorize/info | Get OAuth Authorization Consent Screen Info |
| [**getOAuthServerMetadata()**](OAuthApi.md#getOAuthServerMetadata) | **GET** /.well-known/oauth-authorization-server | Get OAuth Authorization Server Metadata |
| [**registerOAuthClient()**](OAuthApi.md#registerOAuthClient) | **POST** /oauth/register | Register Dynamic OAuth Client |
| [**revokeOAuthToken()**](OAuthApi.md#revokeOAuthToken) | **POST** /oauth/revoke | Revoke OAuth Token |


## `approveOAuthAuthorization()`

```php
approveOAuthAuthorization($approveOAuthAuthorizationRequest): \Omnismith\Sdk\Model\ApproveOAuthAuthorization200Response
```

Approve OAuth Authorization Consent

Approves client access to a specific Omnismith project and generates an authorization code.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$approveOAuthAuthorizationRequest = new \Omnismith\Sdk\Model\ApproveOAuthAuthorizationRequest(); // \Omnismith\Sdk\Model\ApproveOAuthAuthorizationRequest

try {
    $result = $apiInstance->approveOAuthAuthorization($approveOAuthAuthorizationRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->approveOAuthAuthorization: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **approveOAuthAuthorizationRequest** | [**\Omnismith\Sdk\Model\ApproveOAuthAuthorizationRequest**](../Model/ApproveOAuthAuthorizationRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\ApproveOAuthAuthorization200Response**](../Model/ApproveOAuthAuthorization200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `exchangeOAuthToken()`

```php
exchangeOAuthToken($oAuthTokenRequest): \Omnismith\Sdk\Model\ExchangeOAuthToken200Response
```

Exchange OAuth 2.0 Token

Exchanges an authorization code or refresh token for a standard RS256 JWT access token (RFC 6749 / RFC 7636).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$oAuthTokenRequest = new \Omnismith\Sdk\Model\OAuthTokenRequest(); // \Omnismith\Sdk\Model\OAuthTokenRequest

try {
    $result = $apiInstance->exchangeOAuthToken($oAuthTokenRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->exchangeOAuthToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **oAuthTokenRequest** | [**\Omnismith\Sdk\Model\OAuthTokenRequest**](../Model/OAuthTokenRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\ExchangeOAuthToken200Response**](../Model/ExchangeOAuthToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getJwks()`

```php
getJwks(): \Omnismith\Sdk\Model\GetJwks200Response
```

Get JSON Web Key Set

Returns the JSON Web Key Set (RFC 7517) containing the active public cryptographic keys used to verify RS256 JWT access tokens issued by the platform.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getJwks();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getJwks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\GetJwks200Response**](../Model/GetJwks200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOAuthAuthorizeInfo()`

```php
getOAuthAuthorizeInfo($clientId, $redirectUri, $responseType, $scope, $codeChallenge, $codeChallengeMethod, $state): \Omnismith\Sdk\Model\GetOAuthAuthorizeInfo200Response
```

Get OAuth Authorization Consent Screen Info

Retrieves client metadata, requested scopes, verified user identity, and accessible projects to render the OAuth consent interface.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$clientId = omni_client_0195a8f2c3e471238000000000000001; // string | Registered OAuth client identifier
$redirectUri = https://claude.ai/api/mcp/oauth_callback; // string | Target redirection URI matching registered client URIs
$responseType = code; // string | OAuth response type (must be \"code\")
$scope = omnismith:all; // string | Space-delimited requested scopes
$codeChallenge = E9Melhoa2OwvFrGMTJguCH5SZXgk6uKUaz312M20O48; // string | PKCE code challenge string (RFC 7636)
$codeChallengeMethod = S256; // string | PKCE code challenge transformation method
$state = state_xyz123; // string | Opaque client state parameter for CSRF mitigation

try {
    $result = $apiInstance->getOAuthAuthorizeInfo($clientId, $redirectUri, $responseType, $scope, $codeChallenge, $codeChallengeMethod, $state);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getOAuthAuthorizeInfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **clientId** | **string**| Registered OAuth client identifier | |
| **redirectUri** | **string**| Target redirection URI matching registered client URIs | |
| **responseType** | **string**| OAuth response type (must be \&quot;code\&quot;) | [default to &#39;code&#39;] |
| **scope** | **string**| Space-delimited requested scopes | [optional] |
| **codeChallenge** | **string**| PKCE code challenge string (RFC 7636) | [optional] |
| **codeChallengeMethod** | **string**| PKCE code challenge transformation method | [optional] [default to &#39;S256&#39;] |
| **state** | **string**| Opaque client state parameter for CSRF mitigation | [optional] |

### Return type

[**\Omnismith\Sdk\Model\GetOAuthAuthorizeInfo200Response**](../Model/GetOAuthAuthorizeInfo200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOAuthServerMetadata()`

```php
getOAuthServerMetadata(): \Omnismith\Sdk\Model\GetOAuthServerMetadata200Response
```

Get OAuth Authorization Server Metadata

Returns OAuth 2.0 Authorization Server Metadata (RFC 8414) defining the endpoints, supported grant types, and PKCE challenge methods for automated client configuration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getOAuthServerMetadata();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->getOAuthServerMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\GetOAuthServerMetadata200Response**](../Model/GetOAuthServerMetadata200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `registerOAuthClient()`

```php
registerOAuthClient($registerOAuthClientRequest): \Omnismith\Sdk\Model\RegisterOAuthClient201Response
```

Register Dynamic OAuth Client

Dynamically registers a new OAuth client per RFC 7591 (Dynamic Client Registration). Generates unique client credentials and registers authorized callback redirection URIs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$registerOAuthClientRequest = new \Omnismith\Sdk\Model\RegisterOAuthClientRequest(); // \Omnismith\Sdk\Model\RegisterOAuthClientRequest

try {
    $result = $apiInstance->registerOAuthClient($registerOAuthClientRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->registerOAuthClient: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **registerOAuthClientRequest** | [**\Omnismith\Sdk\Model\RegisterOAuthClientRequest**](../Model/RegisterOAuthClientRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\RegisterOAuthClient201Response**](../Model/RegisterOAuthClient201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeOAuthToken()`

```php
revokeOAuthToken($revokeOAuthTokenRequest): \Omnismith\Sdk\Model\RevokeOAuthToken200Response
```

Revoke OAuth Token

Revokes an issued OAuth access token or refresh token per RFC 7009 (Token Revocation). Returns success even if the token was already revoked or expired.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\OAuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$revokeOAuthTokenRequest = new \Omnismith\Sdk\Model\RevokeOAuthTokenRequest(); // \Omnismith\Sdk\Model\RevokeOAuthTokenRequest

try {
    $result = $apiInstance->revokeOAuthToken($revokeOAuthTokenRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OAuthApi->revokeOAuthToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **revokeOAuthTokenRequest** | [**\Omnismith\Sdk\Model\RevokeOAuthTokenRequest**](../Model/RevokeOAuthTokenRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\RevokeOAuthToken200Response**](../Model/RevokeOAuthToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
