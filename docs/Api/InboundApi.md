# Omnismith\Sdk\InboundApi

Inbound

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addInboundEndpointSecret()**](InboundApi.md#addInboundEndpointSecret) | **POST** /templates/{templateId}/inbound-endpoints/{id}/secrets | Add a secret to an inbound endpoint (start a rotation) |
| [**createTemplateInboundEndpoint()**](InboundApi.md#createTemplateInboundEndpoint) | **POST** /templates/{templateId}/inbound-endpoints | Create an inbound endpoint on a template |
| [**deleteInboundEndpointSecret()**](InboundApi.md#deleteInboundEndpointSecret) | **DELETE** /templates/{templateId}/inbound-endpoints/{id}/secrets/{secretId} | Remove a secret from an inbound endpoint (finish a rotation) |
| [**deleteTemplateInboundEndpoint()**](InboundApi.md#deleteTemplateInboundEndpoint) | **DELETE** /templates/{templateId}/inbound-endpoints/{id} | Delete an inbound endpoint |
| [**getInboundDelivery()**](InboundApi.md#getInboundDelivery) | **GET** /templates/{templateId}/inbound-endpoints/{id}/deliveries/{deliveryId} | Get one delivery an inbound endpoint received |
| [**getTemplateInboundEndpoint()**](InboundApi.md#getTemplateInboundEndpoint) | **GET** /templates/{templateId}/inbound-endpoints/{id} | Get an inbound endpoint |
| [**listInboundDeliveries()**](InboundApi.md#listInboundDeliveries) | **GET** /templates/{templateId}/inbound-endpoints/{id}/deliveries | List the deliveries an inbound endpoint received |
| [**listTemplateInboundEndpoints()**](InboundApi.md#listTemplateInboundEndpoints) | **GET** /templates/{templateId}/inbound-endpoints | List the inbound endpoints of a template |
| [**previewInboundMapping()**](InboundApi.md#previewInboundMapping) | **POST** /templates/{templateId}/inbound-endpoints/{id}/preview | Preview what an inbound mapping does with a sample payload |
| [**receiveInboundDelivery()**](InboundApi.md#receiveInboundDelivery) | **POST** /inbound/{projectId}/{endpointId} | Receive a delivery from an outside system |
| [**replayInboundDelivery()**](InboundApi.md#replayInboundDelivery) | **POST** /templates/{templateId}/inbound-endpoints/{id}/deliveries/{deliveryId}/replay | Replay a stored inbound delivery through the current mapping |
| [**updateTemplateInboundEndpoint()**](InboundApi.md#updateTemplateInboundEndpoint) | **PATCH** /templates/{templateId}/inbound-endpoints/{id} | Update an inbound endpoint |


## `addInboundEndpointSecret()`

```php
addInboundEndpointSecret($templateId, $id, $xOmnismithProjectId, $addInboundEndpointSecretRequest): \Omnismith\Sdk\Model\InboundSecretRevealed
```

Add a secret to an inbound endpoint (start a rotation)

Adds a second secret. Deliveries signed with either secret are accepted until the old one is removed with `deleteInboundEndpointSecret`. An endpoint holds at most two secrets. The body may be empty to have the secret generated.  The response carries the secret once and never again: give it to whoever configures the sender and do not store it anywhere else. Like updating the endpoint, this requires your own permission to create and edit records of the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$addInboundEndpointSecretRequest = new \Omnismith\Sdk\Model\AddInboundEndpointSecretRequest(); // \Omnismith\Sdk\Model\AddInboundEndpointSecretRequest

try {
    $result = $apiInstance->addInboundEndpointSecret($templateId, $id, $xOmnismithProjectId, $addInboundEndpointSecretRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->addInboundEndpointSecret: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **addInboundEndpointSecretRequest** | [**\Omnismith\Sdk\Model\AddInboundEndpointSecretRequest**](../Model/AddInboundEndpointSecretRequest.md)|  | [optional] |

### Return type

[**\Omnismith\Sdk\Model\InboundSecretRevealed**](../Model/InboundSecretRevealed.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createTemplateInboundEndpoint()`

```php
createTemplateInboundEndpoint($templateId, $createInboundEndpointRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\InboundEndpointCreatedResponse
```

Create an inbound endpoint on a template

Creates a public URL through which an outside system (Stripe, GitHub, a form tool, a device) writes records into the template without an Omnismith credential. Pick the sender's `signature` preset and describe the `mapping` from the payload to the template's attributes.  The response carries the receive URL to configure in the sender and, once only, the secret the sender signs with. Hand both to the user, once, for pasting into the sender. Do not repeat the secret later and never store it in a record: it is never returned again, and a lost secret is replaced with `addInboundEndpointSecret` (the `add_inbound_endpoint_secret` tool).  To verify the feed: check the mapping on a sample event from the sender's documentation with `previewInboundMapping` (the `preview_inbound_mapping` tool), ask the user to send a test event, then read `listInboundDeliveries` (the `list_inbound_deliveries` tool).  An endpoint lets its sender create and edit the template's records, so creating one also requires your own permission to create and edit records of the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$createInboundEndpointRequest = new \Omnismith\Sdk\Model\CreateInboundEndpointRequest(); // \Omnismith\Sdk\Model\CreateInboundEndpointRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->createTemplateInboundEndpoint($templateId, $createInboundEndpointRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->createTemplateInboundEndpoint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **createInboundEndpointRequest** | [**\Omnismith\Sdk\Model\CreateInboundEndpointRequest**](../Model/CreateInboundEndpointRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\InboundEndpointCreatedResponse**](../Model/InboundEndpointCreatedResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteInboundEndpointSecret()`

```php
deleteInboundEndpointSecret($templateId, $id, $secretId, $xOmnismithProjectId)
```

Remove a secret from an inbound endpoint (finish a rotation)

Deliveries signed with this secret are rejected from now on. An endpoint keeps at least one secret, so the last one cannot be removed (422).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$secretId = 01a0f0e2-7c1a-7000-8000-0000000000c1; // string | Secret UUID, from the endpoint's `secrets`
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->deleteInboundEndpointSecret($templateId, $id, $secretId, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->deleteInboundEndpointSecret: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **secretId** | **string**| Secret UUID, from the endpoint&#39;s &#x60;secrets&#x60; | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteTemplateInboundEndpoint()`

```php
deleteTemplateInboundEndpoint($templateId, $id, $xOmnismithProjectId)
```

Delete an inbound endpoint

Deletes the endpoint. Its URL answers 404 from then on, so the sender's deliveries stop being accepted. Records it wrote are not affected.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $apiInstance->deleteTemplateInboundEndpoint($templateId, $id, $xOmnismithProjectId);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->deleteTemplateInboundEndpoint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInboundDelivery()`

```php
getInboundDelivery($templateId, $id, $deliveryId, $xOmnismithProjectId): \Omnismith\Sdk\Model\InboundDeliveryDetail
```

Get one delivery an inbound endpoint received

One row of the delivery log with the stored body (at most 256 KB), the allow-listed headers, and `error`: for a rejected or partial delivery, the per-record `items` and field `errors` it was answered with. `deliveryId` is the `log_id` the sender was answered with. The stored body can serve as the sample for `previewInboundMapping` (`delivery_id`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$deliveryId = 01a0f0e2-7c1a-7000-8000-0000000000d1; // string | Delivery log row UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->getInboundDelivery($templateId, $id, $deliveryId, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->getInboundDelivery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **deliveryId** | **string**| Delivery log row UUID | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\InboundDeliveryDetail**](../Model/InboundDeliveryDetail.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTemplateInboundEndpoint()`

```php
getTemplateInboundEndpoint($templateId, $id, $xOmnismithProjectId): \Omnismith\Sdk\Model\InboundEndpointResponse
```

Get an inbound endpoint

Returns the endpoint with its receive URL. Secret values are never returned; each secret shows only a hint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->getTemplateInboundEndpoint($templateId, $id, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->getTemplateInboundEndpoint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\InboundEndpointResponse**](../Model/InboundEndpointResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listInboundDeliveries()`

```php
listInboundDeliveries($templateId, $id, $xOmnismithProjectId, $outcome, $from, $to, $limit, $offset): \Omnismith\Sdk\Model\ListInboundDeliveries200Response
```

List the deliveries an inbound endpoint received

The endpoint's delivery log, newest first: every delivery that passed signature verification, and at most one signature failure per 10 seconds. Rows are kept for 7 days. Bodies are left out; read one delivery for its body and headers.  This is how a feed is verified after a test event. On `rejected` or `partial`, read the delivery with `getInboundDelivery` (the `get_inbound_delivery` tool) for its per-record errors, fix the mapping with `updateTemplateInboundEndpoint` (the `update_template_inbound_endpoint` tool), then recover it with `replayInboundDelivery` (the `replay_inbound_delivery` tool). A `401` row (`reason` `mismatch` or `missing_signature`) usually means the sender is configured with the wrong secret or header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
$outcome = ["rejected","failed"]; // string[] | Only deliveries with one of these outcomes; comma-separated
$from = 2026-10-01T00:00:00Z; // \DateTime | Only deliveries received at or after this RFC 3339 time
$to = 2026-10-01T23:59:59Z; // \DateTime | Only deliveries received at or before this RFC 3339 time
$limit = 20; // int | Page size
$offset = 0; // int | Number of deliveries to skip

try {
    $result = $apiInstance->listInboundDeliveries($templateId, $id, $xOmnismithProjectId, $outcome, $from, $to, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->listInboundDeliveries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
| **outcome** | [**string[]**](../Model/string.md)| Only deliveries with one of these outcomes; comma-separated | [optional] |
| **from** | **\DateTime**| Only deliveries received at or after this RFC 3339 time | [optional] |
| **to** | **\DateTime**| Only deliveries received at or before this RFC 3339 time | [optional] |
| **limit** | **int**| Page size | [optional] [default to 20] |
| **offset** | **int**| Number of deliveries to skip | [optional] [default to 0] |

### Return type

[**\Omnismith\Sdk\Model\ListInboundDeliveries200Response**](../Model/ListInboundDeliveries200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplateInboundEndpoints()`

```php
listTemplateInboundEndpoints($templateId, $xOmnismithProjectId): \Omnismith\Sdk\Model\ListTemplateInboundEndpoints200Response
```

List the inbound endpoints of a template

Returns every inbound endpoint that writes records into the template, in creation order, each with its receive URL, signature, mapping and secret hints. Secret values are never returned. The schema overview (`get_schema_overview`) already lists each template's endpoints in brief.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->listTemplateInboundEndpoints($templateId, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->listTemplateInboundEndpoints: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ListTemplateInboundEndpoints200Response**](../Model/ListTemplateInboundEndpoints200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `previewInboundMapping()`

```php
previewInboundMapping($templateId, $id, $previewInboundMappingRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\PreviewInboundMapping200Response
```

Preview what an inbound mapping does with a sample payload

A dry run: maps a sample payload with the endpoint's mapping, or with an unsaved `mapping` to try, and reports what each record would become. Nothing is written.  Use it before saving a mapping and before asking the sender for a test event: pass the sample event from the sender's documentation as `body`, or a delivery from the endpoint's log as `delivery_id`.  The answer says whether the `match` conditions hold, and per record: the external key, whether it would `create` or `update` a record (and which), the attribute values after list and reference resolution, in the write API's shape, and the error a real delivery would meet: mapping errors, type errors and rule violations, keyed as on receive (`items[i].attributes.<slug>`). A mapping that does not fit the template, or an `items` path that names no list, is answered with 422.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$previewInboundMappingRequest = new \Omnismith\Sdk\Model\PreviewInboundMappingRequest(); // \Omnismith\Sdk\Model\PreviewInboundMappingRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->previewInboundMapping($templateId, $id, $previewInboundMappingRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->previewInboundMapping: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **previewInboundMappingRequest** | [**\Omnismith\Sdk\Model\PreviewInboundMappingRequest**](../Model/PreviewInboundMappingRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\PreviewInboundMapping200Response**](../Model/PreviewInboundMapping200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `receiveInboundDelivery()`

```php
receiveInboundDelivery($projectId, $endpointId, $requestBody): \Omnismith\Sdk\Model\ReceiveInboundDelivery200Response
```

Receive a delivery from an outside system

The receive URL of an inbound endpoint, called by the sending system rather than by API clients. It takes no Omnismith credential: every delivery must carry a valid signature for the endpoint.  - `200` — `processed`: every record was written. `partial`: some records failed; `errors` and `items` say which, and a replay recovers them. `skipped`: nothing was processed, with `reason` `match` (the mapping's conditions did not hold), `no_items` (the items list was empty) or `duplicate` (the delivery id was already processed). - `400` — the body is not a JSON object or array. - `401` — the signature is missing or does not verify; `reason` says why. - `404` — no enabled endpoint at this URL. - `422` — no record could be written; `errors` are keyed `items[i].attributes.<slug>`, as the entity write API keys them. - `409`, `429`, `5xx` — the delivery could not be written right now (a key conflict, a quota or rate limit); retry later. - `413` — the body is over 1 MB.  Every answer after signature verification carries `log_id`, the delivery's row in the endpoint's delivery log.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$projectId = 'projectId_example'; // string | Project UUID
$endpointId = 'endpointId_example'; // string | Inbound endpoint UUID
$requestBody = NULL; // array<string,mixed> | The sender's JSON payload, unchanged. At most 1 MB.

try {
    $result = $apiInstance->receiveInboundDelivery($projectId, $endpointId, $requestBody);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->receiveInboundDelivery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **projectId** | **string**| Project UUID | |
| **endpointId** | **string**| Inbound endpoint UUID | |
| **requestBody** | [**array<string,mixed>**](../Model/mixed.md)| The sender&#39;s JSON payload, unchanged. At most 1 MB. | |

### Return type

[**\Omnismith\Sdk\Model\ReceiveInboundDelivery200Response**](../Model/ReceiveInboundDelivery200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `replayInboundDelivery()`

```php
replayInboundDelivery($templateId, $id, $deliveryId, $xOmnismithProjectId): \Omnismith\Sdk\Model\InboundDeliverySummary
```

Replay a stored inbound delivery through the current mapping

Recovers a delivery after the mapping or the template was fixed: re-runs the endpoint's current mapping on the stored body and writes the records, attributed to the endpoint as on receive. The signature is not verified again (only verified deliveries are stored) and the duplicate check is skipped.  Only `rejected`, `failed` and `partial` deliveries are replayed; for a `partial` one, only the records that failed. A processed or skipped delivery, one that failed signature verification (nothing of it was stored), and one whose stored body was truncated are refused with 409.  The replay is a new row in the delivery log, returned here, with `replay_of` naming the replayed delivery and `replayed_by` the user who asked. Its `outcome` says whether the records were written now.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$deliveryId = 01a0f0e2-7c1a-7000-8000-0000000000d1; // string | The delivery log row to replay
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->replayInboundDelivery($templateId, $id, $deliveryId, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->replayInboundDelivery: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **deliveryId** | **string**| The delivery log row to replay | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\InboundDeliverySummary**](../Model/InboundDeliverySummary.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTemplateInboundEndpoint()`

```php
updateTemplateInboundEndpoint($templateId, $id, $updateInboundEndpointRequest, $xOmnismithProjectId): \Omnismith\Sdk\Model\InboundEndpointResponse
```

Update an inbound endpoint

Partial update: send only the fields to change. `delivery_id_source: null` removes the delivery id source. Set `enabled: false` to stop accepting deliveries without deleting the endpoint. Secrets are changed with the secrets endpoints, never here.  Try a mapping change first with `previewInboundMapping` (the `preview_inbound_mapping` tool), which takes an unsaved `mapping`. After saving, recover the deliveries the old mapping rejected with `replayInboundDelivery` (the `replay_inbound_delivery` tool).  Like create, this requires your own permission to create and edit records of the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\InboundApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = customer; // string | UUID or slug of the template
$id = 01a0f0e2-7c1a-7000-8000-000000000001; // string | Inbound endpoint UUID
$updateInboundEndpointRequest = new \Omnismith\Sdk\Model\UpdateInboundEndpointRequest(); // \Omnismith\Sdk\Model\UpdateInboundEndpointRequest
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.

try {
    $result = $apiInstance->updateTemplateInboundEndpoint($templateId, $id, $updateInboundEndpointRequest, $xOmnismithProjectId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboundApi->updateTemplateInboundEndpoint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| UUID or slug of the template | |
| **id** | **string**| Inbound endpoint UUID | |
| **updateInboundEndpointRequest** | [**\Omnismith\Sdk\Model\UpdateInboundEndpointRequest**](../Model/UpdateInboundEndpointRequest.md)|  | |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |

### Return type

[**\Omnismith\Sdk\Model\InboundEndpointResponse**](../Model/InboundEndpointResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
