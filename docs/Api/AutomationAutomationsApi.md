# Omnismith\AutomationAutomationsApi



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
createAutomation($create_automation_request): \Omnismith\Model\CreateAttributeItem201Response
```

Create a new automation

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_automation_request = new \Omnismith\Model\CreateAutomationRequest(); // \Omnismith\Model\CreateAutomationRequest

try {
    $result = $apiInstance->createAutomation($create_automation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->createAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_automation_request** | [**\Omnismith\Model\CreateAutomationRequest**](../Model/CreateAutomationRequest.md)|  | |

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
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
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
getAutomation($id): \Omnismith\Model\AutomationResponse
```

Get an automation by ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
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

[**\Omnismith\Model\AutomationResponse**](../Model/AutomationResponse.md)

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
listAutomationExecutions($id, $limit, $offset, $status): \Omnismith\Model\ListAutomationExecutions200Response
```

List automation executions

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
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

[**\Omnismith\Model\ListAutomationExecutions200Response**](../Model/ListAutomationExecutions200Response.md)

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
listAutomations($template_id, $is_enabled): \Omnismith\Model\AutomationResponse[]
```

List automations

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 'template_id_example'; // string | Filter by template ID
$is_enabled = True; // bool | Filter by enabled status

try {
    $result = $apiInstance->listAutomations($template_id, $is_enabled);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->listAutomations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Filter by template ID | [optional] |
| **is_enabled** | **bool**| Filter by enabled status | [optional] |

### Return type

[**\Omnismith\Model\AutomationResponse[]**](../Model/AutomationResponse.md)

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
toggleAutomation($id, $toggle_automation_request): \Omnismith\Model\AutomationResponse
```

Toggle automation enabled status

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$toggle_automation_request = new \Omnismith\Model\ToggleAutomationRequest(); // \Omnismith\Model\ToggleAutomationRequest

try {
    $result = $apiInstance->toggleAutomation($id, $toggle_automation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->toggleAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **toggle_automation_request** | [**\Omnismith\Model\ToggleAutomationRequest**](../Model/ToggleAutomationRequest.md)|  | |

### Return type

[**\Omnismith\Model\AutomationResponse**](../Model/AutomationResponse.md)

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
updateAutomation($id, $update_automation_request)
```

Update an automation

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\AutomationAutomationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_automation_request = new \Omnismith\Model\UpdateAutomationRequest(); // \Omnismith\Model\UpdateAutomationRequest

try {
    $apiInstance->updateAutomation($id, $update_automation_request);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->updateAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_automation_request** | [**\Omnismith\Model\UpdateAutomationRequest**](../Model/UpdateAutomationRequest.md)|  | |

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
