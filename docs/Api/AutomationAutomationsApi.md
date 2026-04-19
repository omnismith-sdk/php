# Omnismith\Sdk\AutomationAutomationsApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAutomation()**](AutomationAutomationsApi.md#createAutomation) | **POST** /automation/automations | Create a new automation |
| [**deleteAutomation()**](AutomationAutomationsApi.md#deleteAutomation) | **DELETE** /automation/automations/{id} | Delete an automation |
| [**getAutomation()**](AutomationAutomationsApi.md#getAutomation) | **GET** /automation/automations/{id} | Get an automation by ID |
| [**listAutomationExecutions()**](AutomationAutomationsApi.md#listAutomationExecutions) | **GET** /automation/automations/{id}/executions | List automation executions |
| [**listAutomations()**](AutomationAutomationsApi.md#listAutomations) | **GET** /automation/automations | List automations |
| [**toggleAutomation()**](AutomationAutomationsApi.md#toggleAutomation) | **PATCH** /automation/automations/{id}/toggle | Toggle automation enabled status |
| [**updateAutomation()**](AutomationAutomationsApi.md#updateAutomation) | **PUT** /automation/automations/{id} | Update an automation |


## `createAutomation()`

```php
createAutomation($createAutomationRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Create a new automation

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createAutomationRequest = new \Omnismith\Sdk\Model\CreateAutomationRequest(); // \Omnismith\Sdk\Model\CreateAutomationRequest

try {
    $result = $apiInstance->createAutomation($createAutomationRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->createAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createAutomationRequest** | [**\Omnismith\Sdk\Model\CreateAutomationRequest**](../Model/CreateAutomationRequest.md)|  | |

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

## `deleteAutomation()`

```php
deleteAutomation($id)
```

Delete an automation

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteAutomation($id);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->deleteAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

## `getAutomation()`

```php
getAutomation($id): \Omnismith\Sdk\Model\AutomationResponse
```

Get an automation by ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->getAutomation($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->getAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Omnismith\Sdk\Model\AutomationResponse**](../Model/AutomationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAutomationExecutions()`

```php
listAutomationExecutions($id, $limit, $offset, $status): \Omnismith\Sdk\Model\ListAutomationExecutions200Response
```

List automation executions

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Automation ID
$limit = 20; // int | Number of results
$offset = 0; // int | Pagination offset
$status = 'status_example'; // string | Filter by status

try {
    $result = $apiInstance->listAutomationExecutions($id, $limit, $offset, $status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->listAutomationExecutions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Automation ID | |
| **limit** | **int**| Number of results | [optional] [default to 20] |
| **offset** | **int**| Pagination offset | [optional] [default to 0] |
| **status** | **string**| Filter by status | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ListAutomationExecutions200Response**](../Model/ListAutomationExecutions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAutomations()`

```php
listAutomations($templateId, $isEnabled): \Omnismith\Sdk\Model\AutomationResponse[]
```

List automations

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = 'templateId_example'; // string | Filter by template ID
$isEnabled = True; // bool | Filter by enabled status

try {
    $result = $apiInstance->listAutomations($templateId, $isEnabled);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->listAutomations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Filter by template ID | [optional] |
| **isEnabled** | **bool**| Filter by enabled status | [optional] |

### Return type

[**\Omnismith\Sdk\Model\AutomationResponse[]**](../Model/AutomationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `toggleAutomation()`

```php
toggleAutomation($id, $toggleAutomationRequest): \Omnismith\Sdk\Model\AutomationResponse
```

Toggle automation enabled status

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$toggleAutomationRequest = new \Omnismith\Sdk\Model\ToggleAutomationRequest(); // \Omnismith\Sdk\Model\ToggleAutomationRequest

try {
    $result = $apiInstance->toggleAutomation($id, $toggleAutomationRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->toggleAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **toggleAutomationRequest** | [**\Omnismith\Sdk\Model\ToggleAutomationRequest**](../Model/ToggleAutomationRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\AutomationResponse**](../Model/AutomationResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateAutomation()`

```php
updateAutomation($id, $updateAutomationRequest)
```

Update an automation

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$updateAutomationRequest = new \Omnismith\Sdk\Model\UpdateAutomationRequest(); // \Omnismith\Sdk\Model\UpdateAutomationRequest

try {
    $apiInstance->updateAutomation($id, $updateAutomationRequest);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->updateAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **updateAutomationRequest** | [**\Omnismith\Sdk\Model\UpdateAutomationRequest**](../Model/UpdateAutomationRequest.md)|  | |

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
