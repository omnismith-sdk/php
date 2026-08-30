# Omnismith\Sdk\AuthApi

Auth

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getMyPermissions()**](AuthApi.md#getMyPermissions) | **GET** /auth/me/permissions | Get current user role permissions |
| [**googleLogin()**](AuthApi.md#googleLogin) | **POST** /auth/google-login | Authenticate or register with Google Sign-In |
| [**googleLoginRedirect()**](AuthApi.md#googleLoginRedirect) | **POST** /auth/google-login-redirect | Google OAuth callback redirect handler |
| [**listSessions()**](AuthApi.md#listSessions) | **GET** /auth/sessions | List active and historical user sessions |
| [**login()**](AuthApi.md#login) | **POST** /auth/login | Authenticate user with email and password |
| [**refreshToken()**](AuthApi.md#refreshToken) | **POST** /auth/refresh | Rotate refresh token and issue new access token |
| [**revokeSession()**](AuthApi.md#revokeSession) | **DELETE** /auth/sessions/{id} | Revoke an active login session |
| [**switchProject()**](AuthApi.md#switchProject) | **POST** /auth/switch-project | Switch active project context |


## `getMyPermissions()`

```php
getMyPermissions(): \Omnismith\Sdk\Model\GetMyPermissions200Response
```

Get current user role permissions

Returns the complete list of permission strings granted to the authenticated user under their active project role. Returns `[\"*\"]` for project owners who possess full root administrative privileges, or an array of granular permission keys (e.g. `entity.view`, `template.create`, `billing.view_usage`) for custom assigned roles. Returns an empty array if no role is currently assigned.

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

Authenticate or register with Google Sign-In

Authenticates a user using a Google Identity Services (GIS) ID token. Verifies the cryptographic token signature against Google public keys. If no account exists for the verified email address, a new user account is automatically provisioned and verified. Returns a JWT access token and refresh token for the active session.

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

## `googleLoginRedirect()`

```php
googleLoginRedirect($credential, $gCsrfToken)
```

Google OAuth callback redirect handler

Handles Google Identity Services form-urlencoded POST redirection (`credential` and `g_csrf_token`). Authenticates or provisions the user account, initiates an active session, and redirects the browser (HTTP 302) to the frontend application callback URL with JWT access and refresh tokens embedded in the URL fragment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$credential = 'credential_example'; // string | Google ID token credential issued by Google Identity Services
$gCsrfToken = 'gCsrfToken_example'; // string | CSRF token provided by Google Identity Services

try {
    $apiInstance->googleLoginRedirect($credential, $gCsrfToken);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->googleLoginRedirect: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **credential** | **string**| Google ID token credential issued by Google Identity Services | |
| **gCsrfToken** | **string**| CSRF token provided by Google Identity Services | [optional] |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSessions()`

```php
listSessions(): \Omnismith\Sdk\Model\ListSessions200Response
```

List active and historical user sessions

Retrieves all login sessions recorded for the authenticated user across devices and browsers. Each session record includes client metadata (IP address, User-Agent), issuance timestamp, expiration date, current status (`active`, `expired`, `revoked`), and revocation details if applicable.

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

Authenticate user with email and password

Authenticates an existing user account using email and password. Upon successful validation, generates an active login session and returns a short-lived JWT access token and a refresh token for rotating credentials.

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

Rotate refresh token and issue new access token

Exchanges a valid refresh token for a newly issued JWT access token and a rotated refresh token. Implements strict single-use refresh token rotation: the supplied refresh token is permanently invalidated upon successful exchange. If an expired, already-rotated, or revoked token is presented, the request is rejected.

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

Revoke an active login session

Immediately revokes a specific user login session by its unique session ID. All refresh tokens issued within this session are invalidated, preventing further token refreshes. If the revoked session corresponds to the current client connection, subsequent refresh attempts will fail.

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
$id = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a; // string | Unique UUID identifier of the session to revoke

try {
    $apiInstance->revokeSession($id);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->revokeSession: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID identifier of the session to revoke | |

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

## `switchProject()`

```php
switchProject($switchProjectRequest): \Omnismith\Sdk\Model\SwitchProject200Response
```

Switch active project context

Switches the active multi-tenancy project context for the authenticated user session. Verifies that the user is an active member or owner of the target project, then issues a new JWT access token and refresh token containing updated claims for the selected project_id and the user's assigned role.

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

[**\Omnismith\Sdk\Model\SwitchProject200Response**](../Model/SwitchProject200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
