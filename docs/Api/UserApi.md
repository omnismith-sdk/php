# Omnismith\Sdk\UserApi

User

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**confirmUserEmail()**](UserApi.md#confirmUserEmail) | **GET** /users/confirm-email | Confirm a user&#39;s email address using a confirmation token |
| [**registerUser()**](UserApi.md#registerUser) | **POST** /users/register | Register a new user |
| [**resendConfirmationEmail()**](UserApi.md#resendConfirmationEmail) | **POST** /users/resend-confirmation | Resend the email confirmation link |


## `confirmUserEmail()`

```php
confirmUserEmail($token): \Omnismith\Sdk\Model\ConfirmUserEmail200Response
```

Confirm a user's email address using a confirmation token

Validates an email confirmation token sent to a newly registered user's email address and activates the account upon success. If the token is valid, returns a success confirmation message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token = cf_token_abc123xyz; // string | The email confirmation token received via email

try {
    $result = $apiInstance->confirmUserEmail($token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->confirmUserEmail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**| The email confirmation token received via email | |

### Return type

[**\Omnismith\Sdk\Model\ConfirmUserEmail200Response**](../Model/ConfirmUserEmail200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `registerUser()`

```php
registerUser($registerUserRequest): \Omnismith\Sdk\Model\CreateProject201Response
```

Register a new user

Registers a new user account with email and password. For unauthenticated / public signups, a Cloudflare Turnstile `captchaToken` is required to prevent bot abuse. Sends a confirmation link to the provided email address upon creation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$registerUserRequest = new \Omnismith\Sdk\Model\RegisterUserRequest(); // \Omnismith\Sdk\Model\RegisterUserRequest

try {
    $result = $apiInstance->registerUser($registerUserRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->registerUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **registerUserRequest** | [**\Omnismith\Sdk\Model\RegisterUserRequest**](../Model/RegisterUserRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateProject201Response**](../Model/CreateProject201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `resendConfirmationEmail()`

```php
resendConfirmationEmail($resendConfirmationEmailRequest): \Omnismith\Sdk\Model\ResendConfirmationEmail200Response
```

Resend the email confirmation link

Resends the account verification email with an activation link for unconfirmed accounts. Rate-limited to prevent abuse. Silently succeeds if the email is not registered for security.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$resendConfirmationEmailRequest = new \Omnismith\Sdk\Model\ResendConfirmationEmailRequest(); // \Omnismith\Sdk\Model\ResendConfirmationEmailRequest

try {
    $result = $apiInstance->resendConfirmationEmail($resendConfirmationEmailRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->resendConfirmationEmail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **resendConfirmationEmailRequest** | [**\Omnismith\Sdk\Model\ResendConfirmationEmailRequest**](../Model/ResendConfirmationEmailRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\ResendConfirmationEmail200Response**](../Model/ResendConfirmationEmail200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
