# Omnismith\Sdk\FeedbackApi

Feedback

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**sendFeedback()**](FeedbackApi.md#sendFeedback) | **POST** /feedback | Submit user feedback |


## `sendFeedback()`

```php
sendFeedback($sendFeedbackRequest)
```

Submit user feedback

Sends a feedback email to the Omnismith support team on behalf of the authenticated user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\FeedbackApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$sendFeedbackRequest = new \Omnismith\Sdk\Model\SendFeedbackRequest(); // \Omnismith\Sdk\Model\SendFeedbackRequest

try {
    $apiInstance->sendFeedback($sendFeedbackRequest);
} catch (Exception $e) {
    echo 'Exception when calling FeedbackApi->sendFeedback: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **sendFeedbackRequest** | [**\Omnismith\Sdk\Model\SendFeedbackRequest**](../Model/SendFeedbackRequest.md)|  | |

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
