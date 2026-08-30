# Omnismith\Sdk\AutomationAutomationsApi



All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAutomation()**](AutomationAutomationsApi.md#createAutomation) | **POST** /automation/automations | Create an automation rule |
| [**deleteAutomation()**](AutomationAutomationsApi.md#deleteAutomation) | **DELETE** /automation/automations/{id} | Delete an automation |
| [**getAutomation()**](AutomationAutomationsApi.md#getAutomation) | **GET** /automation/automations/{id} | Get an automation by ID |
| [**listAutomationExecutions()**](AutomationAutomationsApi.md#listAutomationExecutions) | **GET** /automation/automations/{id}/executions | List automation execution logs |
| [**listAutomations()**](AutomationAutomationsApi.md#listAutomations) | **GET** /automation/automations | List project automations |
| [**toggleAutomation()**](AutomationAutomationsApi.md#toggleAutomation) | **PATCH** /automation/automations/{id}/toggle | Toggle automation enabled status |
| [**updateAutomation()**](AutomationAutomationsApi.md#updateAutomation) | **PUT** /automation/automations/{id} | Update an automation |


## `createAutomation()`

```php
createAutomation($createAutomationRequest): \Omnismith\Sdk\Model\CreateAutomation201Response
```

Create an automation rule

Creates a new event-driven automation rule within the current project. Configures event trigger criteria (such as `on_entity_created`, `on_entity_updated`, or `on_attribute_changed`), multi-condition filters evaluating attribute values (using operators `eq`, `neq`, `gt`, `gte`, `lt`, `lte`, `contains`, `not_contains`, `is_empty`, `is_not_empty` across current value or delta modes), automated action targets (`telegram`, `webhook`, `push`), and an optional cooldown window in seconds to throttle repeated firings for the same entity.

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

[**\Omnismith\Sdk\Model\CreateAutomation201Response**](../Model/CreateAutomation201Response.md)

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

Permanently deletes an automation rule by UUID, unbinding event listeners and stopping all future evaluations and action dispatches for that rule.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60001; // string | Unique automation UUID to delete

try {
    $apiInstance->deleteAutomation($id);
} catch (Exception $e) {
    echo 'Exception when calling AutomationAutomationsApi->deleteAutomation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique automation UUID to delete | |

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

Retrieves the complete configuration of a specific automation rule by its UUID, including trigger event types, template/attribute references, condition comparison expressions, action payloads, execution cooldown interval, and the timestamp of its last execution.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60001; // string | Unique automation UUID

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
| **id** | **string**| Unique automation UUID | |

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

List automation execution logs

Retrieves paginated execution logs and audit history for a specific automation rule. Each execution log records the triggering entity ID, trigger timestamp, execution completion time, final status (`pending`, `success`, `partial_failure`, `failed`), detailed action dispatch outcomes with error messages, and top-level execution errors.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60001; // string | Automation UUID to fetch execution history for
$limit = 20; // int | Maximum number of execution log entries to return per page
$offset = 0; // int | Number of execution log records to skip for pagination
$status = success; // string | Filter execution logs by execution outcome status

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
| **id** | **string**| Automation UUID to fetch execution history for | |
| **limit** | **int**| Maximum number of execution log entries to return per page | [optional] [default to 20] |
| **offset** | **int**| Number of execution log records to skip for pagination | [optional] [default to 0] |
| **status** | **string**| Filter execution logs by execution outcome status | [optional] |

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

List project automations

Retrieves all automation rules configured within the current project context. Automations define event-driven workflows triggered by entity lifecycle events (such as entity creation, attribute updates, or metric threshold changes), evaluated against multi-attribute conditions, and dispatched to configured action channels (Telegram, webhooks, mobile push). Results can be filtered by entity template or active status.

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
$templateId = 01912ecb-4654-7890-a1b2-c3d4e5f60088; // string | Filter automations scoped to a specific entity template UUID
$isEnabled = true; // bool | Filter automations by active enabled status (true for active rules, false for paused rules)

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
| **templateId** | **string**| Filter automations scoped to a specific entity template UUID | [optional] |
| **isEnabled** | **bool**| Filter automations by active enabled status (true for active rules, false for paused rules) | [optional] |

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

Enables or pauses an automation rule without altering its trigger definitions, condition criteria, or action configurations. Paused automations are ignored during event processing.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60001; // string | Unique automation UUID to toggle
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
| **id** | **string**| Unique automation UUID to toggle | |
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

Updates an existing automation rule by UUID. Supports modifying rule name, description, trigger event definitions, condition filter criteria, action dispatches, and cooldown throttle settings.

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
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60001; // string | Unique automation UUID to update
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
| **id** | **string**| Unique automation UUID to update | |
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
