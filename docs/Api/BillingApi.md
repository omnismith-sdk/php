# Omnismith\BillingApi

Billing

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCheckout()**](BillingApi.md#createCheckout) | **POST** /billing/checkout | Create a checkout session for subscription |
| [**getAllTiers()**](BillingApi.md#getAllTiers) | **GET** /billing/tiers | List all available tiers |
| [**getPortalUrl()**](BillingApi.md#getPortalUrl) | **GET** /billing/portal | Get customer portal URL |
| [**getUsageInsights()**](BillingApi.md#getUsageInsights) | **GET** /billing/usage/insights | Get current tier usage insights |
| [**getUserTier()**](BillingApi.md#getUserTier) | **GET** /billing/tier | Get current user tier |
| [**logAiUsage()**](BillingApi.md#logAiUsage) | **POST** /billing/log-usage | Log AI usage credits |


## `createCheckout()`

```php
createCheckout($create_checkout_request): \Omnismith\Model\CheckoutResponse
```

Create a checkout session for subscription

Creates a LemonSqueezy checkout session to subscribe to a paid tier. Returns a URL to redirect the user to complete payment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_checkout_request = new \Omnismith\Model\CreateCheckoutRequest(); // \Omnismith\Model\CreateCheckoutRequest

try {
    $result = $apiInstance->createCheckout($create_checkout_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->createCheckout: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_checkout_request** | [**\Omnismith\Model\CreateCheckoutRequest**](../Model/CreateCheckoutRequest.md)|  | |

### Return type

[**\Omnismith\Model\CheckoutResponse**](../Model/CheckoutResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAllTiers()`

```php
getAllTiers(): \Omnismith\Model\GetAllTiers200Response
```

List all available tiers

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getAllTiers();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->getAllTiers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\GetAllTiers200Response**](../Model/GetAllTiers200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPortalUrl()`

```php
getPortalUrl(): \Omnismith\Model\PortalUrlResponse
```

Get customer portal URL

Returns a LemonSqueezy customer portal URL where users can manage their subscription (cancel, update payment method, view invoices).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getPortalUrl();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->getPortalUrl: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\PortalUrlResponse**](../Model/PortalUrlResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUsageInsights()`

```php
getUsageInsights(): \Omnismith\Model\UsageInsightsResponse
```

Get current tier usage insights

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getUsageInsights();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->getUsageInsights: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\UsageInsightsResponse**](../Model/UsageInsightsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUserTier()`

```php
getUserTier(): \Omnismith\Model\TierResponse
```

Get current user tier

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getUserTier();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->getUserTier: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\TierResponse**](../Model/TierResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `logAiUsage()`

```php
logAiUsage($log_ai_usage_request): \Omnismith\Model\LogAiUsage200Response
```

Log AI usage credits

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$log_ai_usage_request = new \Omnismith\Model\LogAiUsageRequest(); // \Omnismith\Model\LogAiUsageRequest

try {
    $result = $apiInstance->logAiUsage($log_ai_usage_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->logAiUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **log_ai_usage_request** | [**\Omnismith\Model\LogAiUsageRequest**](../Model/LogAiUsageRequest.md)|  | |

### Return type

[**\Omnismith\Model\LogAiUsage200Response**](../Model/LogAiUsage200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
