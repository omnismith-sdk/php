# Omnismith\FeedbackApi

Feedback

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**sendFeedback()**](FeedbackApi.md#sendFeedback) | **POST** /feedback | Submit user feedback |


## `sendFeedback()`

```php
sendFeedback($send_feedback_request)
```

Submit user feedback

Sends a feedback email to the Omnismith support team on behalf of the authenticated user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\FeedbackApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_feedback_request = new \Omnismith\Model\SendFeedbackRequest(); // \Omnismith\Model\SendFeedbackRequest

try {
    $apiInstance->sendFeedback($send_feedback_request);
} catch (Exception $e) {
    echo 'Exception when calling FeedbackApi->sendFeedback: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_feedback_request** | [**\Omnismith\Model\SendFeedbackRequest**](../Model/SendFeedbackRequest.md)|  | |

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
