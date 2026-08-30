# Omnismith\Sdk\AutomationPushDevicesApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listPushDevices()**](AutomationPushDevicesApi.md#listPushDevices) | **GET** /automation/push-devices | List registered push devices |
| [**registerPushDevice()**](AutomationPushDevicesApi.md#registerPushDevice) | **POST** /automation/push-devices | Register a mobile push notification device |
| [**unregisterPushDevice()**](AutomationPushDevicesApi.md#unregisterPushDevice) | **DELETE** /automation/push-devices | Unregister a mobile push notification device |


## `listPushDevices()`

```php
listPushDevices(): \Omnismith\Sdk\Model\ListPushDevices200Response
```

List registered push devices

Retrieves all Firebase Cloud Messaging (FCM) mobile push devices registered under the authenticated user account for receiving automated push alerts. Device registration tokens are masked in the output for security.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationPushDevicesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listPushDevices();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationPushDevicesApi->listPushDevices: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListPushDevices200Response**](../Model/ListPushDevices200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `registerPushDevice()`

```php
registerPushDevice($registerPushDeviceRequest): \Omnismith\Sdk\Model\RegisterPushDevice201Response
```

Register a mobile push notification device

Registers an FCM device token under the authenticated user account to receive real-time push notifications from automation action triggers. If the token is already registered, its device name and activity timestamp are updated.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationPushDevicesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$registerPushDeviceRequest = new \Omnismith\Sdk\Model\RegisterPushDeviceRequest(); // \Omnismith\Sdk\Model\RegisterPushDeviceRequest

try {
    $result = $apiInstance->registerPushDevice($registerPushDeviceRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationPushDevicesApi->registerPushDevice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **registerPushDeviceRequest** | [**\Omnismith\Sdk\Model\RegisterPushDeviceRequest**](../Model/RegisterPushDeviceRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\RegisterPushDevice201Response**](../Model/RegisterPushDevice201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `unregisterPushDevice()`

```php
unregisterPushDevice($unregisterPushDeviceRequest)
```

Unregister a mobile push notification device

Removes an FCM push notification device token from the authenticated user profile, stopping all future automation push notifications directed to that device.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationPushDevicesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$unregisterPushDeviceRequest = new \Omnismith\Sdk\Model\UnregisterPushDeviceRequest(); // \Omnismith\Sdk\Model\UnregisterPushDeviceRequest

try {
    $apiInstance->unregisterPushDevice($unregisterPushDeviceRequest);
} catch (Exception $e) {
    echo 'Exception when calling AutomationPushDevicesApi->unregisterPushDevice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **unregisterPushDeviceRequest** | [**\Omnismith\Sdk\Model\UnregisterPushDeviceRequest**](../Model/UnregisterPushDeviceRequest.md)|  | |

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
