# Omnismith\AutomationNotificationChannelsApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createNotificationChannel()**](AutomationNotificationChannelsApi.md#createNotificationChannel) | **POST** /automation/notification-channels | Create a new notification channel |
| [**deleteNotificationChannel()**](AutomationNotificationChannelsApi.md#deleteNotificationChannel) | **DELETE** /automation/notification-channels/{id} | Delete a notification channel |
| [**getNotificationChannel()**](AutomationNotificationChannelsApi.md#getNotificationChannel) | **GET** /automation/notification-channels/{id} | Get a notification channel |
| [**listNotificationChannels()**](AutomationNotificationChannelsApi.md#listNotificationChannels) | **GET** /automation/notification-channels | List all notification channels |
| [**testNotificationChannel()**](AutomationNotificationChannelsApi.md#testNotificationChannel) | **POST** /automation/notification-channels/{id}/test | Send a test message via the notification channel |
| [**updateNotificationChannel()**](AutomationNotificationChannelsApi.md#updateNotificationChannel) | **PUT** /automation/notification-channels/{id} | Update a notification channel |


## `createNotificationChannel()`

```php
createNotificationChannel($create_notification_channel_request): \Omnismith\Model\CreateAttributeItem201Response
```

Create a new notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_notification_channel_request = new \Omnismith\Model\CreateNotificationChannelRequest(); // \Omnismith\Model\CreateNotificationChannelRequest

try {
    $result = $apiInstance->createNotificationChannel($create_notification_channel_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->createNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_notification_channel_request** | [**\Omnismith\Model\CreateNotificationChannelRequest**](../Model/CreateNotificationChannelRequest.md)|  | |

### Return type

[**\Omnismith\Model\CreateAttributeItem201Response**](../Model/CreateAttributeItem201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteNotificationChannel()`

```php
deleteNotificationChannel($id)
```

Delete a notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel UUID

try {
    $apiInstance->deleteNotificationChannel($id);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->deleteNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel UUID | |

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

## `getNotificationChannel()`

```php
getNotificationChannel($id): \Omnismith\Model\NotificationChannelResponse
```

Get a notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel UUID

try {
    $result = $apiInstance->getNotificationChannel($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->getNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel UUID | |

### Return type

[**\Omnismith\Model\NotificationChannelResponse**](../Model/NotificationChannelResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listNotificationChannels()`

```php
listNotificationChannels(): \Omnismith\Model\ListNotificationChannels200Response
```

List all notification channels

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listNotificationChannels();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->listNotificationChannels: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Model\ListNotificationChannels200Response**](../Model/ListNotificationChannels200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `testNotificationChannel()`

```php
testNotificationChannel($id, $test_notification_channel_request): \Omnismith\Model\TestNotificationChannel200Response
```

Send a test message via the notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel UUID
$test_notification_channel_request = new \Omnismith\Model\TestNotificationChannelRequest(); // \Omnismith\Model\TestNotificationChannelRequest

try {
    $result = $apiInstance->testNotificationChannel($id, $test_notification_channel_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->testNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel UUID | |
| **test_notification_channel_request** | [**\Omnismith\Model\TestNotificationChannelRequest**](../Model/TestNotificationChannelRequest.md)|  | |

### Return type

[**\Omnismith\Model\TestNotificationChannel200Response**](../Model/TestNotificationChannel200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateNotificationChannel()`

```php
updateNotificationChannel($id, $update_notification_channel_request)
```

Update a notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel UUID
$update_notification_channel_request = new \Omnismith\Model\UpdateNotificationChannelRequest(); // \Omnismith\Model\UpdateNotificationChannelRequest

try {
    $apiInstance->updateNotificationChannel($id, $update_notification_channel_request);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->updateNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel UUID | |
| **update_notification_channel_request** | [**\Omnismith\Model\UpdateNotificationChannelRequest**](../Model/UpdateNotificationChannelRequest.md)|  | |

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
