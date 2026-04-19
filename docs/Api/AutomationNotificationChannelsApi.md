# Omnismith\Sdk\AutomationNotificationChannelsApi



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
createNotificationChannel($createNotificationChannelRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Create a new notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createNotificationChannelRequest = new \Omnismith\Sdk\Model\CreateNotificationChannelRequest(); // \Omnismith\Sdk\Model\CreateNotificationChannelRequest

try {
    $result = $apiInstance->createNotificationChannel($createNotificationChannelRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->createNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createNotificationChannelRequest** | [**\Omnismith\Sdk\Model\CreateNotificationChannelRequest**](../Model/CreateNotificationChannelRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateAttributeItem201Response**](../Model/CreateAttributeItem201Response.md)

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
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationNotificationChannelsApi(
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
getNotificationChannel($id): \Omnismith\Sdk\Model\NotificationChannelResponse
```

Get a notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationNotificationChannelsApi(
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

[**\Omnismith\Sdk\Model\NotificationChannelResponse**](../Model/NotificationChannelResponse.md)

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
listNotificationChannels(): \Omnismith\Sdk\Model\ListNotificationChannels200Response
```

List all notification channels

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationNotificationChannelsApi(
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

[**\Omnismith\Sdk\Model\ListNotificationChannels200Response**](../Model/ListNotificationChannels200Response.md)

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
testNotificationChannel($id, $testNotificationChannelRequest): \Omnismith\Sdk\Model\TestNotificationChannel200Response
```

Send a test message via the notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel UUID
$testNotificationChannelRequest = new \Omnismith\Sdk\Model\TestNotificationChannelRequest(); // \Omnismith\Sdk\Model\TestNotificationChannelRequest

try {
    $result = $apiInstance->testNotificationChannel($id, $testNotificationChannelRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->testNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel UUID | |
| **testNotificationChannelRequest** | [**\Omnismith\Sdk\Model\TestNotificationChannelRequest**](../Model/TestNotificationChannelRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\TestNotificationChannel200Response**](../Model/TestNotificationChannel200Response.md)

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
updateNotificationChannel($id, $updateNotificationChannelRequest)
```

Update a notification channel

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationNotificationChannelsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Channel UUID
$updateNotificationChannelRequest = new \Omnismith\Sdk\Model\UpdateNotificationChannelRequest(); // \Omnismith\Sdk\Model\UpdateNotificationChannelRequest

try {
    $apiInstance->updateNotificationChannel($id, $updateNotificationChannelRequest);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->updateNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Channel UUID | |
| **updateNotificationChannelRequest** | [**\Omnismith\Sdk\Model\UpdateNotificationChannelRequest**](../Model/UpdateNotificationChannelRequest.md)|  | |

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
