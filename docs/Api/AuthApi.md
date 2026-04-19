# Omnismith\Sdk\AuthApi

Auth

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getMyPermissions()**](AuthApi.md#getMyPermissions) | **GET** /auth/me/permissions | Get current user&#39;s role permissions |
| [**googleLogin()**](AuthApi.md#googleLogin) | **POST** /auth/google-login | Login or register via Google Sign-In |
| [**listSessions()**](AuthApi.md#listSessions) | **GET** /auth/sessions | List recent login sessions |
| [**login()**](AuthApi.md#login) | **POST** /auth/login | Login user |
| [**refreshToken()**](AuthApi.md#refreshToken) | **POST** /auth/refresh | Refresh access token |
| [**revokeSession()**](AuthApi.md#revokeSession) | **DELETE** /auth/sessions/{id} | Revoke a login session |
| [**switchProject()**](AuthApi.md#switchProject) | **POST** /auth/switch-project | Switch active project context |


## `getMyPermissions()`

```php
getMyPermissions(): \Omnismith\Sdk\Model\GetMyPermissions200Response
```

Get current user's role permissions

Returns the permissions for the authenticated user's current role. Returns [\"*\"] for project owners (full access) or an empty array if no role is assigned.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getMyPermissions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->getMyPermissions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\GetMyPermissions200Response**](../Model/GetMyPermissions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `googleLogin()`

```php
googleLogin($googleLoginRequest): \Omnismith\Sdk\Model\GoogleLogin200Response
```

Login or register via Google Sign-In

Authenticates a user using a Google ID token. If the user does not exist, a new account is automatically created.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$googleLoginRequest = new \Omnismith\Sdk\Model\GoogleLoginRequest(); // \Omnismith\Sdk\Model\GoogleLoginRequest

try {
    $result = $apiInstance->googleLogin($googleLoginRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->googleLogin: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **googleLoginRequest** | [**\Omnismith\Sdk\Model\GoogleLoginRequest**](../Model/GoogleLoginRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\GoogleLogin200Response**](../Model/GoogleLogin200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSessions()`

```php
listSessions(): \Omnismith\Sdk\Model\ListSessions200Response
```

List recent login sessions

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listSessions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->listSessions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListSessions200Response**](../Model/ListSessions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `login()`

```php
login($loginRequest): \Omnismith\Sdk\Model\GoogleLogin200Response
```

Login user

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$loginRequest = new \Omnismith\Sdk\Model\LoginRequest(); // \Omnismith\Sdk\Model\LoginRequest

try {
    $result = $apiInstance->login($loginRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->login: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **loginRequest** | [**\Omnismith\Sdk\Model\LoginRequest**](../Model/LoginRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\GoogleLogin200Response**](../Model/GoogleLogin200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `refreshToken()`

```php
refreshToken($refreshTokenRequest): \Omnismith\Sdk\Model\RefreshToken200Response
```

Refresh access token

Exchange a valid refresh token for a new access token and refresh token. The old refresh token is invalidated (rotation).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$refreshTokenRequest = new \Omnismith\Sdk\Model\RefreshTokenRequest(); // \Omnismith\Sdk\Model\RefreshTokenRequest

try {
    $result = $apiInstance->refreshToken($refreshTokenRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->refreshToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **refreshTokenRequest** | [**\Omnismith\Sdk\Model\RefreshTokenRequest**](../Model/RefreshTokenRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\RefreshToken200Response**](../Model/RefreshToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeSession()`

```php
revokeSession($id)
```

Revoke a login session

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Session ID

try {
    $apiInstance->revokeSession($id);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->revokeSession: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Session ID | |

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

## `switchProject()`

```php
switchProject($switchProjectRequest): \Omnismith\Sdk\Model\GoogleLogin200Response
```

Switch active project context

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$switchProjectRequest = new \Omnismith\Sdk\Model\SwitchProjectRequest(); // \Omnismith\Sdk\Model\SwitchProjectRequest

try {
    $result = $apiInstance->switchProject($switchProjectRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->switchProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **switchProjectRequest** | [**\Omnismith\Sdk\Model\SwitchProjectRequest**](../Model/SwitchProjectRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\GoogleLogin200Response**](../Model/GoogleLogin200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
