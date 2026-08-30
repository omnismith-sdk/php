# Omnismith\Sdk\AutomationNotificationChannelsApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createNotificationChannel()**](AutomationNotificationChannelsApi.md#createNotificationChannel) | **POST** /automation/notification-channels | Create a notification channel |
| [**deleteNotificationChannel()**](AutomationNotificationChannelsApi.md#deleteNotificationChannel) | **DELETE** /automation/notification-channels/{id} | Delete a notification channel |
| [**getNotificationChannel()**](AutomationNotificationChannelsApi.md#getNotificationChannel) | **GET** /automation/notification-channels/{id} | Get a notification channel by ID |
| [**listNotificationChannels()**](AutomationNotificationChannelsApi.md#listNotificationChannels) | **GET** /automation/notification-channels | List notification channels |
| [**testNotificationChannel()**](AutomationNotificationChannelsApi.md#testNotificationChannel) | **POST** /automation/notification-channels/{id}/test | Send a test notification message |
| [**updateNotificationChannel()**](AutomationNotificationChannelsApi.md#updateNotificationChannel) | **PUT** /automation/notification-channels/{id} | Update a notification channel |


## `createNotificationChannel()`

```php
createNotificationChannel($createNotificationChannelRequest): \Omnismith\Sdk\Model\CreateNotificationChannel201Response
```

Create a notification channel

Registers a new external notification channel for the current project. Channels can be of type `telegram` (configured with a Telegram bot token), `webhook` (configured with endpoint URL, custom HTTP headers, and authentication methods such as bearer token or basic auth), or `push` (FCM mobile push notifications). Configured channels can then be linked as target actions in automation rules.

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

[**\Omnismith\Sdk\Model\CreateNotificationChannel201Response**](../Model/CreateNotificationChannel201Response.md)

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

Permanently removes a notification channel from the project by UUID. Automations referencing this channel must be updated to prevent dispatch delivery failures.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60002; // string | Unique notification channel UUID to delete

try {
    $apiInstance->deleteNotificationChannel($id);
} catch (Exception $e) {
    echo 'Exception when calling AutomationNotificationChannelsApi->deleteNotificationChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique notification channel UUID to delete | |

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

Get a notification channel by ID

Retrieves configuration details and status of a specific notification channel by its UUID, including channel type, name, creation timestamp, and credential settings for authorized project administrators.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60002; // string | Unique notification channel UUID

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
| **id** | **string**| Unique notification channel UUID | |

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

List notification channels

Retrieves all notification delivery channels configured within the current project. Channels are reusable destination targets for automation alerts, supporting Telegram bots, external HTTP webhooks, and mobile push notifications. Sensitive credentials are sanitized in list outputs.

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

Send a test notification message

Dispatches an immediate test notification message to verify channel credentials, network reachability, and recipient configuration. Accepts channel-specific parameters such as Telegram `chat_id` or push notification `title` and `message`.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60002; // string | Unique notification channel UUID to test
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
| **id** | **string**| Unique notification channel UUID to test | |
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

Updates an existing notification channel configuration by UUID. Allows updating the channel display name or updating integration credentials (such as new bot tokens, webhook endpoints, or authentication credentials).

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60002; // string | Unique notification channel UUID to update
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
| **id** | **string**| Unique notification channel UUID to update | |
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
