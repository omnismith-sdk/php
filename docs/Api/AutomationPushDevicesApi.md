# Omnismith\Sdk\AutomationPushDevicesApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listPushDevices()**](AutomationPushDevicesApi.md#listPushDevices) | **GET** /automation/push-devices | List the current user&#39;s registered push devices |
| [**registerPushDevice()**](AutomationPushDevicesApi.md#registerPushDevice) | **POST** /automation/push-devices | Register a push notification device token |
| [**unregisterPushDevice()**](AutomationPushDevicesApi.md#unregisterPushDevice) | **DELETE** /automation/push-devices | Unregister a push notification device token |


## `listPushDevices()`

```php
listPushDevices(): \Omnismith\Sdk\Model\ListPushDevices200Response
```

List the current user's registered push devices

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
registerPushDevice($registerPushDeviceRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Register a push notification device token

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

[**\Omnismith\Sdk\Model\CreateAttributeItem201Response**](../Model/CreateAttributeItem201Response.md)

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

Unregister a push notification device token

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
