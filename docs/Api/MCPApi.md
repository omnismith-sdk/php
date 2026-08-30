# Omnismith\Sdk\MCPApi

MCP

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAttribute()**](MCPApi.md#createAttribute) | **POST** /attributes | Create a new attribute |
| [**createAttributeItem()**](MCPApi.md#createAttributeItem) | **POST** /attributes/{id}/items | Add a list item to an attribute |
| [**createAutomation()**](MCPApi.md#createAutomation) | **POST** /automation/automations | Create an automation rule |
| [**createDashboard()**](MCPApi.md#createDashboard) | **POST** /dashboards | Create a new dashboard |
| [**createDashboardBlock()**](MCPApi.md#createDashboardBlock) | **POST** /dashboards/{dashboardId}/blocks | Create a new block in a dashboard |
| [**createEntity()**](MCPApi.md#createEntity) | **POST** /entities | Create a new dynamic entity |
| [**createNotificationChannel()**](MCPApi.md#createNotificationChannel) | **POST** /automation/notification-channels | Create a notification channel |
| [**createTemplate()**](MCPApi.md#createTemplate) | **POST** /templates | Create a new template |
| [**createWorkspace()**](MCPApi.md#createWorkspace) | **POST** /workspaces | Create a new workspace |
| [**createWorkspaceView()**](MCPApi.md#createWorkspaceView) | **POST** /workspaces/{id}/views | Add a new view / pane to a workspace |
| [**deleteAttribute()**](MCPApi.md#deleteAttribute) | **DELETE** /attributes/{id} | Delete an attribute |
| [**deleteAttributeReferenceConfig()**](MCPApi.md#deleteAttributeReferenceConfig) | **DELETE** /attributes/{id}/reference | Delete reference configuration for an attribute |
| [**deleteAutomation()**](MCPApi.md#deleteAutomation) | **DELETE** /automation/automations/{id} | Delete an automation |
| [**deleteDashboard()**](MCPApi.md#deleteDashboard) | **DELETE** /dashboards/{id} | Delete a dashboard |
| [**deleteDashboardBlock()**](MCPApi.md#deleteDashboardBlock) | **DELETE** /dashboards/{dashboardId}/blocks/{blockId} | Delete a dashboard block |
| [**deleteEntity()**](MCPApi.md#deleteEntity) | **DELETE** /entities/{id} | Soft-delete an entity record |
| [**deleteNotificationChannel()**](MCPApi.md#deleteNotificationChannel) | **DELETE** /automation/notification-channels/{id} | Delete a notification channel |
| [**deleteTemplate()**](MCPApi.md#deleteTemplate) | **DELETE** /templates/{id} | Delete a template |
| [**deleteWorkspace()**](MCPApi.md#deleteWorkspace) | **DELETE** /workspaces/{id} | Delete a workspace and its views |
| [**deleteWorkspaceView()**](MCPApi.md#deleteWorkspaceView) | **DELETE** /workspaces/{id}/views/{viewId} | Delete a view / pane from a workspace |
| [**getAttribute()**](MCPApi.md#getAttribute) | **GET** /attributes/{id} | Get an attribute by ID |
| [**getAttributeReferenceConfig()**](MCPApi.md#getAttributeReferenceConfig) | **GET** /attributes/{id}/reference | Get reference configuration for an attribute |
| [**getAutomation()**](MCPApi.md#getAutomation) | **GET** /automation/automations/{id} | Get an automation by ID |
| [**getDashboard()**](MCPApi.md#getDashboard) | **GET** /dashboards/{id} | Get a dashboard by ID |
| [**getDashboardBlock()**](MCPApi.md#getDashboardBlock) | **GET** /dashboards/{dashboardId}/blocks/{blockId} | Get a dashboard block by ID |
| [**getEntity()**](MCPApi.md#getEntity) | **GET** /entities/{id} | Get an entity record by ID |
| [**getEntityChart()**](MCPApi.md#getEntityChart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory()**](MCPApi.md#getEntityHistory) | **GET** /entities/{id}/history | Get entity dimension change history |
| [**getMarketplaceBlueprint()**](MCPApi.md#getMarketplaceBlueprint) | **GET** /marketplace/blueprints/{id} | Get marketplace blueprint details |
| [**getNotificationChannel()**](MCPApi.md#getNotificationChannel) | **GET** /automation/notification-channels/{id} | Get a notification channel by ID |
| [**getProjectSchema()**](MCPApi.md#getProjectSchema) | **GET** /discovery/project-schema | Get complete project schema graph |
| [**getTemplate()**](MCPApi.md#getTemplate) | **GET** /templates/{id} | Get a template by ID or slug |
| [**getUsageInsights()**](MCPApi.md#getUsageInsights) | **GET** /billing/usage/insights | Get current tier usage insights |
| [**getWorkspace()**](MCPApi.md#getWorkspace) | **GET** /workspaces/{id} | Get workspace details and its views |
| [**getWorkspaceView()**](MCPApi.md#getWorkspaceView) | **GET** /workspaces/{id}/views/{viewId} | Get details of a workspace view / pane |
| [**ingestEntityMetrics()**](MCPApi.md#ingestEntityMetrics) | **POST** /entities/{id}/metrics | Ingest high-frequency metric observations for an entity |
| [**installMarketplaceBlueprint()**](MCPApi.md#installMarketplaceBlueprint) | **POST** /marketplace/blueprints/{id}/install | Install a marketplace blueprint into a project |
| [**listAttributeItems()**](MCPApi.md#listAttributeItems) | **GET** /attributes/{id}/items | List items of an attribute |
| [**listAttributes()**](MCPApi.md#listAttributes) | **GET** /attributes | List all attributes |
| [**listAuditLogs()**](MCPApi.md#listAuditLogs) | **GET** /audit-logs | List project audit logs |
| [**listAutomations()**](MCPApi.md#listAutomations) | **GET** /automation/automations | List project automations |
| [**listDashboardBlocks()**](MCPApi.md#listDashboardBlocks) | **GET** /dashboards/{dashboardId}/blocks | List all blocks in a dashboard |
| [**listDashboards()**](MCPApi.md#listDashboards) | **GET** /dashboards | List all dashboards |
| [**listNotificationChannels()**](MCPApi.md#listNotificationChannels) | **GET** /automation/notification-channels | List notification channels |
| [**listTemplateEntityCounts()**](MCPApi.md#listTemplateEntityCounts) | **GET** /templates/entity-counts | List entity counts per template |
| [**listTemplates()**](MCPApi.md#listTemplates) | **GET** /templates | List all templates |
| [**listWorkspaces()**](MCPApi.md#listWorkspaces) | **GET** /workspaces | List all workspaces for current project |
| [**patchAttribute()**](MCPApi.md#patchAttribute) | **PATCH** /attributes/{id} | Patch an attribute (granular partial update) |
| [**patchTemplate()**](MCPApi.md#patchTemplate) | **PATCH** /templates/{id} | Patch a template (granular partial update) |
| [**resolveDashboardBlock()**](MCPApi.md#resolveDashboardBlock) | **GET** /dashboards/{dashboardId}/blocks/{blockId}/resolve | Resolve a dashboard block to its computed data |
| [**searchEntities()**](MCPApi.md#searchEntities) | **POST** /entities/search/{template_id} | Search entities with filtering, sorting, and pagination |
| [**searchMarketplaceBlueprints()**](MCPApi.md#searchMarketplaceBlueprints) | **GET** /marketplace/blueprints | Search marketplace blueprints |
| [**setAttributeItems()**](MCPApi.md#setAttributeItems) | **PUT** /attributes/{id}/items | Set list items for an attribute (replaces all existing items) |
| [**setAttributeReferenceConfig()**](MCPApi.md#setAttributeReferenceConfig) | **PUT** /attributes/{id}/reference | Set or update reference configuration for an attribute |
| [**testNotificationChannel()**](MCPApi.md#testNotificationChannel) | **POST** /automation/notification-channels/{id}/test | Send a test notification message |
| [**toggleAutomation()**](MCPApi.md#toggleAutomation) | **PATCH** /automation/automations/{id}/toggle | Toggle automation enabled status |
| [**updateAttribute()**](MCPApi.md#updateAttribute) | **PUT** /attributes/{id} | Update an attribute (full replacement) |
| [**updateAutomation()**](MCPApi.md#updateAutomation) | **PUT** /automation/automations/{id} | Update an automation |
| [**updateDashboard()**](MCPApi.md#updateDashboard) | **PUT** /dashboards/{id} | Update a dashboard |
| [**updateDashboardBlock()**](MCPApi.md#updateDashboardBlock) | **PUT** /dashboards/{dashboardId}/blocks/{blockId} | Update a dashboard block |
| [**updateEntity()**](MCPApi.md#updateEntity) | **PATCH** /entities/{id} | Update entity attribute values |
| [**updateNotificationChannel()**](MCPApi.md#updateNotificationChannel) | **PUT** /automation/notification-channels/{id} | Update a notification channel |
| [**updateTemplate()**](MCPApi.md#updateTemplate) | **PUT** /templates/{id} | Update a template (full replacement) |
| [**updateWorkspace()**](MCPApi.md#updateWorkspace) | **PUT** /workspaces/{id} | Update workspace metadata and layout |
| [**updateWorkspaceView()**](MCPApi.md#updateWorkspaceView) | **PUT** /workspaces/{id}/views/{viewId} | Update workspace view / pane filters, sort, display mode, or columns |


## `createAttribute()`

```php
createAttribute($createAttributeRequest): \Omnismith\Sdk\Model\CreateAttribute201Response
```

Create a new attribute

Defines a new attribute in the project schema. Attributes can be of kind Dimension (0), Metric (1), List (2), or Reference (3). Specify the storage data type (String: 0, Number: 1, Boolean: 2, Datetime: 3, Date: 4, File: 5, Image: 6, Markdown: 7), name, optional project-unique slug (auto-generated from name if omitted), optional template associations, and an optional reference_config if kind is Reference (3). Subject to project tier quota constraints.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createAttributeRequest = new \Omnismith\Sdk\Model\CreateAttributeRequest(); // \Omnismith\Sdk\Model\CreateAttributeRequest

try {
    $result = $apiInstance->createAttribute($createAttributeRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createAttributeRequest** | [**\Omnismith\Sdk\Model\CreateAttributeRequest**](../Model/CreateAttributeRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateAttribute201Response**](../Model/CreateAttribute201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAttributeItem()`

```php
createAttributeItem($id, $addListItemRequest): \Omnismith\Sdk\Model\CreateAttributeItem201Response
```

Add a list item to an attribute

Appends a single selectable choice option item to a List-type (attribute_type = 2) attribute. Returns the generated or assigned UUID of the newly created list item.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the List-type attribute
$addListItemRequest = new \Omnismith\Sdk\Model\AddListItemRequest(); // \Omnismith\Sdk\Model\AddListItemRequest

try {
    $result = $apiInstance->createAttributeItem($id, $addListItemRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createAttributeItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the List-type attribute | |
| **addListItemRequest** | [**\Omnismith\Sdk\Model\AddListItemRequest**](../Model/AddListItemRequest.md)|  | |

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->createAutomation: ', $e->getMessage(), PHP_EOL;
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

## `createDashboard()`

```php
createDashboard($createDashboardRequest): \Omnismith\Sdk\Model\CreateDashboard201Response
```

Create a new dashboard

Creates a new analytics and telemetry dashboard canvas for organizing metric KPIs, charts, gauges, and entity tables within a customizable grid layout.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createDashboardRequest = new \Omnismith\Sdk\Model\CreateDashboardRequest(); // \Omnismith\Sdk\Model\CreateDashboardRequest | Dashboard creation payload

try {
    $result = $apiInstance->createDashboard($createDashboardRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createDashboardRequest** | [**\Omnismith\Sdk\Model\CreateDashboardRequest**](../Model/CreateDashboardRequest.md)| Dashboard creation payload | |

### Return type

[**\Omnismith\Sdk\Model\CreateDashboard201Response**](../Model/CreateDashboard201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createDashboardBlock()`

```php
createDashboardBlock($dashboardId, $createDashboardBlockRequest): \Omnismith\Sdk\Model\CreateDashboardBlock201Response
```

Create a new block in a dashboard

Creates a new visualization block widget on a dashboard canvas. Supports four block types: stat (single KPI counter of matching entities), chart (time-series telemetry multi-line/bar graph aggregating metric data), gauge (metric threshold gauge with min/max bounds and percentage progress), and list (filtered and sorted entity table). Grid placement is defined via x, y, cols, rows layout parameters.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Target dashboard unique identifier (UUID)
$createDashboardBlockRequest = new \Omnismith\Sdk\Model\CreateDashboardBlockRequest(); // \Omnismith\Sdk\Model\CreateDashboardBlockRequest | Dashboard block creation payload

try {
    $result = $apiInstance->createDashboardBlock($dashboardId, $createDashboardBlockRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Target dashboard unique identifier (UUID) | |
| **createDashboardBlockRequest** | [**\Omnismith\Sdk\Model\CreateDashboardBlockRequest**](../Model/CreateDashboardBlockRequest.md)| Dashboard block creation payload | |

### Return type

[**\Omnismith\Sdk\Model\CreateDashboardBlock201Response**](../Model/CreateDashboardBlock201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createEntity()`

```php
createEntity($createEntityRequest): \Omnismith\Sdk\Model\CreateEntity201Response
```

Create a new dynamic entity

Creates a new dynamic entity record conforming to a template schema.  ### Template Association Specify the target schema via either `template_id` (UUID) or `template_slug` (human-readable slug).  ### Dynamic Attribute Values (`attribute_values`) Each attribute entry supports identifier resolution and accepts either: - `attribute_id`: Canonical attribute UUID - `attribute_slug`: Attribute slug identifier (e.g. `price`, `sku`, `status`)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value (e.g., `\"Wireless Headphones\"`) - **Dimension - Number**: Numeric string representation (e.g., `\"129.99\"`, `\"42\"`) - **Dimension - Boolean**: Strict boolean representation: `\"true\"`, `\"false\"`, `\"1\"`, or `\"0\"` - **Dimension - Date & Datetime**: Formatted as `YYYY-MM-DD` (date) or `YYYY-MM-DD HH:MM:SS` / ISO 8601 `YYYY-MM-DDTHH:MM:SSZ` (datetime) - **Dimension - File & Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined `ListItem` option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced `Entity`  ### Metric Telemetry Persistence Any metric attributes included in `attribute_values` are published directly to the metric ingestion pipeline and recorded in time-series telemetry storage.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createEntityRequest = new \Omnismith\Sdk\Model\CreateEntityRequest(); // \Omnismith\Sdk\Model\CreateEntityRequest

try {
    $result = $apiInstance->createEntity($createEntityRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createEntityRequest** | [**\Omnismith\Sdk\Model\CreateEntityRequest**](../Model/CreateEntityRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateEntity201Response**](../Model/CreateEntity201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->createNotificationChannel: ', $e->getMessage(), PHP_EOL;
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

## `createTemplate()`

```php
createTemplate($createTemplateRequest): \Omnismith\Sdk\Model\CreateTemplate201Response
```

Create a new template

Creates a new dynamic schema template (content type) in the project. Accepts template name, optional description, category, unique slug, attribute bindings, and UI layout groups. Attribute bindings can be defined using structured `attributes` (with optional `default_value` validated against attribute kind/data type) or flat `attribute_ids` / `attribute_slugs`. Visual layout groups organize attributes into 1- or 2-column sections with optional icons. Creating templates is subject to tier quota limits.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createTemplateRequest = new \Omnismith\Sdk\Model\CreateTemplateRequest(); // \Omnismith\Sdk\Model\CreateTemplateRequest

try {
    $result = $apiInstance->createTemplate($createTemplateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createTemplateRequest** | [**\Omnismith\Sdk\Model\CreateTemplateRequest**](../Model/CreateTemplateRequest.md)|  | |

### Return type

[**\Omnismith\Sdk\Model\CreateTemplate201Response**](../Model/CreateTemplate201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createWorkspace()`

```php
createWorkspace($createWorkspaceRequest): \Omnismith\Sdk\Model\CreateDashboard201Response
```

Create a new workspace

Creates a new workspace in the current project context with a specified multi-pane layout (single, split-v, split-h, quad), optional default workspace status, and initial template view bindings to automatically generate panes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$createWorkspaceRequest = new \Omnismith\Sdk\Model\CreateWorkspaceRequest(); // \Omnismith\Sdk\Model\CreateWorkspaceRequest | Workspace creation payload

try {
    $result = $apiInstance->createWorkspace($createWorkspaceRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createWorkspaceRequest** | [**\Omnismith\Sdk\Model\CreateWorkspaceRequest**](../Model/CreateWorkspaceRequest.md)| Workspace creation payload | |

### Return type

[**\Omnismith\Sdk\Model\CreateDashboard201Response**](../Model/CreateDashboard201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createWorkspaceView()`

```php
createWorkspaceView($id, $createWorkspaceViewRequest): \Omnismith\Sdk\Model\CreateDashboardBlock201Response
```

Add a new view / pane to a workspace

Creates and mounts a new view pane within an existing workspace bound to a specific entity schema template, configuring presentation mode (table, grid), visible columns, filter criteria, search queries (keyword or semantic), sorting preferences, and pane order.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Target workspace unique identifier (UUID)
$createWorkspaceViewRequest = new \Omnismith\Sdk\Model\CreateWorkspaceViewRequest(); // \Omnismith\Sdk\Model\CreateWorkspaceViewRequest | Workspace view creation payload

try {
    $result = $apiInstance->createWorkspaceView($id, $createWorkspaceViewRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->createWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Target workspace unique identifier (UUID) | |
| **createWorkspaceViewRequest** | [**\Omnismith\Sdk\Model\CreateWorkspaceViewRequest**](../Model/CreateWorkspaceViewRequest.md)| Workspace view creation payload | |

### Return type

[**\Omnismith\Sdk\Model\CreateDashboardBlock201Response**](../Model/CreateDashboardBlock201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAttribute()`

```php
deleteAttribute($id)
```

Delete an attribute

Soft-deletes an attribute from the project schema. Soft-deleted attributes are removed from active template projections and future queries, while existing historical dimension and telemetry records remain preserved for audit integrity.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to delete

try {
    $apiInstance->deleteAttribute($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to delete | |

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

## `deleteAttributeReferenceConfig()`

```php
deleteAttributeReferenceConfig($id)
```

Delete reference configuration for an attribute

Removes the foreign entity reference configuration mapping from a Reference-type (attribute_type = 3) attribute.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the Reference attribute

try {
    $apiInstance->deleteAttributeReferenceConfig($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the Reference attribute | |

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60001; // string | Unique automation UUID to delete

try {
    $apiInstance->deleteAutomation($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteAutomation: ', $e->getMessage(), PHP_EOL;
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

## `deleteDashboard()`

```php
deleteDashboard($id)
```

Delete a dashboard

Permanently removes a dashboard and all attached visualization blocks, metric widgets, and configurations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Dashboard unique identifier (UUID) to delete

try {
    $apiInstance->deleteDashboard($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Dashboard unique identifier (UUID) to delete | |

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

## `deleteDashboardBlock()`

```php
deleteDashboardBlock($dashboardId, $blockId)
```

Delete a dashboard block

Permanently removes a visualization block widget from the specified dashboard canvas.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID) to delete

try {
    $apiInstance->deleteDashboardBlock($dashboardId, $blockId);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) to delete | |

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

## `deleteEntity()`

```php
deleteEntity($id)
```

Soft-delete an entity record

Marks an entity record as soft-deleted by setting its `deleted_at` timestamp.  Soft-deleted entities are immediately excluded from standard entity searches, BI row queries, and direct retrieval endpoints. Associated historical change logs and time-series telemetry remain preserved for audit compliance.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID) to soft-delete

try {
    $apiInstance->deleteEntity($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) to soft-delete | |

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60002; // string | Unique notification channel UUID to delete

try {
    $apiInstance->deleteNotificationChannel($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteNotificationChannel: ', $e->getMessage(), PHP_EOL;
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

## `deleteTemplate()`

```php
deleteTemplate($id)
```

Delete a template

Soft-deletes a template definition by UUID or slug. Soft-deleted templates are hidden from normal listings, and entity creation under deleted templates is prevented.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to delete

try {
    $apiInstance->deleteTemplate($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to delete | |

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

## `deleteWorkspace()`

```php
deleteWorkspace($id)
```

Delete a workspace and its views

Permanently removes a workspace and all nested view pane configurations from the project.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID) to delete

try {
    $apiInstance->deleteWorkspace($id);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) to delete | |

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

## `deleteWorkspaceView()`

```php
deleteWorkspaceView($id, $viewId)
```

Delete a view / pane from a workspace

Permanently removes a view pane from a workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$viewId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Workspace view unique identifier (UUID) to delete

try {
    $apiInstance->deleteWorkspaceView($id, $viewId);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->deleteWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **viewId** | **string**| Workspace view unique identifier (UUID) to delete | |

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

## `getAttribute()`

```php
getAttribute($id): \Omnismith\Sdk\Model\AttributeResponse
```

Get an attribute by ID

Retrieves complete attribute metadata by its UUID, including kind (Dimension: 0, Metric: 1, List: 2, Reference: 3), storage data type, assigned template IDs, creation timestamps, and reference configuration if applicable.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to fetch

try {
    $result = $apiInstance->getAttribute($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to fetch | |

### Return type

[**\Omnismith\Sdk\Model\AttributeResponse**](../Model/AttributeResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAttributeReferenceConfig()`

```php
getAttributeReferenceConfig($id): \Omnismith\Sdk\Model\ReferenceConfigResponse
```

Get reference configuration for an attribute

Retrieves the relational reference target configuration for a Reference-type (attribute_type = 3) attribute. Returns the target template UUID and target display attribute UUID used for entity reference pointer resolution.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the Reference attribute

try {
    $result = $apiInstance->getAttributeReferenceConfig($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the Reference attribute | |

### Return type

[**\Omnismith\Sdk\Model\ReferenceConfigResponse**](../Model/ReferenceConfigResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->getAutomation: ', $e->getMessage(), PHP_EOL;
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

## `getDashboard()`

```php
getDashboard($id): \Omnismith\Sdk\Model\DashboardResponse
```

Get a dashboard by ID

Retrieves metadata and top-level configuration for a specific dashboard by its unique identifier.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Dashboard unique identifier (UUID)

try {
    $result = $apiInstance->getDashboard($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Dashboard unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\DashboardResponse**](../Model/DashboardResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDashboardBlock()`

```php
getDashboardBlock($dashboardId, $blockId): \Omnismith\Sdk\Model\DashboardBlockResponse
```

Get a dashboard block by ID

Retrieves the configuration details, grid coordinates, and data query definitions for an individual visualization block.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID)

try {
    $result = $apiInstance->getDashboardBlock($dashboardId, $blockId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\DashboardBlockResponse**](../Model/DashboardBlockResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntity()`

```php
getEntity($id, $attributeKey): \Omnismith\Sdk\Model\EntityResponse
```

Get an entity record by ID

Retrieves the full hydrated record for a dynamic entity by its unique identifier (UUID).  ### Attribute Key Formatting (`attribute_key`) The `attribute_key` query parameter controls the dictionary keys in `attribute_values`: - `\"id\"` (default): Keys are canonical attribute UUIDs (e.g. `018b2f1b-8c1a...`). - `\"slug\"`: Keys are human-readable attribute slugs (e.g. `price`, `sku`, `category`), which is recommended for API consumers and AI agent workflows.  ### Hydrated Attribute Values The returned `attribute_values` object includes both raw serialized values and resolved display labels (`custom_value`) for references and list options.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$attributeKey = slug; // string | Format for attribute_values dictionary keys: \"id\" for attribute UUIDs or \"slug\" for human-readable attribute slugs

try {
    $result = $apiInstance->getEntity($id, $attributeKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **attributeKey** | **string**| Format for attribute_values dictionary keys: \&quot;id\&quot; for attribute UUIDs or \&quot;slug\&quot; for human-readable attribute slugs | [optional] [default to &#39;id&#39;] |

### Return type

[**\Omnismith\Sdk\Model\EntityResponse**](../Model/EntityResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntityChart()`

```php
getEntityChart($id, $attributeIds, $start, $end, $aggregateFunc, $bucketWidth): \Omnismith\Sdk\Model\GetEntityChart200Response
```

Get entity chart time-series data

Retrieves aggregated, time-bucketed metric time-series data for an entity.  ### Metric Attribute Filtering (`attribute_ids`) Pass one or more comma-separated metric attribute UUIDs to aggregate across the query window.  ### Aggregation Functions (`aggregate_func`) Supported aggregation operations within each bucket: - `avg` (default): Arithmetic mean of values - `sum`: Sum total of values - `min` / `max`: Minimum / Maximum observed value - `count`: Number of recorded observations - `first` / `last`: Earliest / Latest observation within the time bucket  ### Time Intervals & Bucket Widths (`bucket_width`) Values follow standard time interval notation: `1 second`, `5 seconds`, `10 seconds`, `1 minute` (1m), `5 minutes` (5m), `10 minutes`, `15 minutes`, `30 minutes`, `1 hour` (1h), `6 hours`, `12 hours`, `1 day` (1d), `1 week`, `1 month`.  ### Query Window (`start` & `end`) Query range is defined by `start` and `end` timestamps supplied as integer Unix epoch seconds.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$attributeIds = 018b2f1b-8c1a-75b3-8000-7f0000010010,018b2f1b-8c1a-75b3-8000-7f0000010011; // string | Comma-separated metric attribute UUIDs to aggregate
$start = 1774396800; // int | Start timestamp as Unix epoch in seconds
$end = 1774483200; // int | End timestamp as Unix epoch in seconds
$aggregateFunc = avg; // string | Aggregation function applied within each bucket
$bucketWidth = 1 hour; // string | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day)

try {
    $result = $apiInstance->getEntityChart($id, $attributeIds, $start, $end, $aggregateFunc, $bucketWidth);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getEntityChart: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **attributeIds** | **string**| Comma-separated metric attribute UUIDs to aggregate | |
| **start** | **int**| Start timestamp as Unix epoch in seconds | |
| **end** | **int**| End timestamp as Unix epoch in seconds | |
| **aggregateFunc** | **string**| Aggregation function applied within each bucket | [optional] [default to &#39;avg&#39;] |
| **bucketWidth** | **string**| Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) | [optional] [default to &#39;1 hour&#39;] |

### Return type

[**\Omnismith\Sdk\Model\GetEntityChart200Response**](../Model/GetEntityChart200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEntityHistory()`

```php
getEntityHistory($id, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail): \Omnismith\Sdk\Model\GetEntityHistory200Response
```

Get entity dimension change history

Retrieves the immutable change audit log for an entity's dimension attribute mutations.  ### Dedicated Dimension Audit Log Records all historical mutations to dimension, list, and reference attribute values. High-volume metric telemetry observations bypass this log and are stored in dedicated time-series storage, keeping the audit log clean and performant.  ### Filtering & Search - `attribute_ids`: Filter by one or more comma-separated attribute UUIDs. - `search`: Text search matching historical serialized values. - `start` and `end`: Filter history records within a timestamp window (ISO 8601 or `YYYY-MM-DD HH:MM:SS`). - `author_email`: Filter by the actor who performed the mutation.  ### Pagination & Sorting Supports 1-indexed pagination (`page`, `limit` up to 100) and sorting by `created_at`, `attribute_id`, or `value` (`asc`/`desc`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$page = 1; // int | 1-based page number for pagination
$limit = 20; // int | Number of history records per page (1-100)
$sortBy = created_at; // string | Field to sort change logs by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)
$search = Electronics; // string | Free-text search filter matching against old and new attribute values
$attributeIds = 018b2f1b-8c1a-75b3-8000-7f0000010002,018b2f1b-8c1a-75b3-8000-7f0000010003; // string | Comma-separated attribute UUIDs to filter change history
$start = 2026-08-01T00:00:00Z; // \DateTime | Filter change records occurring on or after this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format)
$end = 2026-08-26T23:59:59Z; // \DateTime | Filter change records occurring on or before this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format)
$authorEmail = demo@omnismith.io; // string | Filter change records by author or actor email

try {
    $result = $apiInstance->getEntityHistory($id, $page, $limit, $sortBy, $sortDirection, $search, $attributeIds, $start, $end, $authorEmail);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getEntityHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **page** | **int**| 1-based page number for pagination | [optional] [default to 1] |
| **limit** | **int**| Number of history records per page (1-100) | [optional] [default to 20] |
| **sortBy** | **string**| Field to sort change logs by | [optional] [default to &#39;created_at&#39;] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;desc&#39;] |
| **search** | **string**| Free-text search filter matching against old and new attribute values | [optional] |
| **attributeIds** | **string**| Comma-separated attribute UUIDs to filter change history | [optional] |
| **start** | **\DateTime**| Filter change records occurring on or after this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) | [optional] |
| **end** | **\DateTime**| Filter change records occurring on or before this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) | [optional] |
| **authorEmail** | **string**| Filter change records by author or actor email | [optional] |

### Return type

[**\Omnismith\Sdk\Model\GetEntityHistory200Response**](../Model/GetEntityHistory200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMarketplaceBlueprint()`

```php
getMarketplaceBlueprint($id): \Omnismith\Sdk\Model\GetMarketplaceBlueprint200Response
```

Get marketplace blueprint details

Retrieves complete information for a specific marketplace blueprint by its UUID. Returns full blueprint metadata, publisher details, popularity metrics, and packaged blueprint schema definition containing template schemas, attribute configurations, and optional demo entities.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60003; // string | Unique marketplace blueprint UUID

try {
    $result = $apiInstance->getMarketplaceBlueprint($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique marketplace blueprint UUID | |

### Return type

[**\Omnismith\Sdk\Model\GetMarketplaceBlueprint200Response**](../Model/GetMarketplaceBlueprint200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->getNotificationChannel: ', $e->getMessage(), PHP_EOL;
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

## `getProjectSchema()`

```php
getProjectSchema(): \Omnismith\Sdk\Model\ProjectSchemaResponse
```

Get complete project schema graph

Retrieves the complete consolidated schema graph for the active project in a single payload. Includes all active attributes, templates (with attribute bindings and UI layout groups), list choice items, and foreign entity reference configurations. Ideal for AI agents, client initialization, metadata caching, and schema introspection.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getProjectSchema();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getProjectSchema: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ProjectSchemaResponse**](../Model/ProjectSchemaResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTemplate()`

```php
getTemplate($id): \Omnismith\Sdk\Model\TemplateResponse
```

Get a template by ID or slug

Retrieves complete template schema details by UUID or unique slug, including ordered attribute bindings, default values per attribute, and visual UI layout groups. Automatically filters out any restricted attributes the caller is not permitted to view.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to retrieve

try {
    $result = $apiInstance->getTemplate($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to retrieve | |

### Return type

[**\Omnismith\Sdk\Model\TemplateResponse**](../Model/TemplateResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUsageInsights()`

```php
getUsageInsights(): \Omnismith\Sdk\Model\UsageInsightsResponse
```

Get current tier usage insights

Returns current resource consumption vs. tier limits for the authenticated user. Includes usage counts (attributes, templates, entities, dashboards, automations, channels, monthly metric ingestions, monthly dimension updates, disk usage, AI credits), corresponding tier limits, and percentage utilization for each resource category. Use this to check quota availability before performing operations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getUsageInsights();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getUsageInsights: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\UsageInsightsResponse**](../Model/UsageInsightsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspace()`

```php
getWorkspace($id): \Omnismith\Sdk\Model\WorkspaceDetailsResponse
```

Get workspace details and its views

Retrieves detailed information for a specific workspace, including its multi-pane layout configuration and all hydrated view panes with their associated template schemas, filter rules, search criteria, column selections, and ordering.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)

try {
    $result = $apiInstance->getWorkspace($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\WorkspaceDetailsResponse**](../Model/WorkspaceDetailsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspaceView()`

```php
getWorkspaceView($id, $viewId): \Omnismith\Sdk\Model\WorkspaceViewResponse
```

Get details of a workspace view / pane

Retrieves complete configuration details for a single workspace view pane, including its schema template binding, active filter rules, search parameters, column visibility, sort order, and layout positioning.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$viewId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Workspace view unique identifier (UUID)

try {
    $result = $apiInstance->getWorkspaceView($id, $viewId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->getWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **viewId** | **string**| Workspace view unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\WorkspaceViewResponse**](../Model/WorkspaceViewResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `ingestEntityMetrics()`

```php
ingestEntityMetrics($id, $ingestMetricsRequest)
```

Ingest high-frequency metric observations for an entity

Ingests time-series metric observations for an entity record.  ### Batch Telemetry Ingestion Accepts a batch array of metric observations (`metric_values`). Each observation targets a metric attribute by `attribute_id` (UUID) or `attribute_slug` and specifies a numeric `value`.  ### High-Throughput Streaming Architecture Metric ingestion calls stream directly into the high-throughput telemetry ingestion pipeline. Asynchronous background consumers persist data points into tenant-scoped time-series storage configured with automated retention and continuous aggregation rollups.  ### Strict Metric Attribute Constraint Only attributes defined with `attribute_type: Metric` are accepted by this endpoint. Mutations to dimension, list, or reference attributes must use `PATCH /entities/{id}` instead.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$ingestMetricsRequest = new \Omnismith\Sdk\Model\IngestMetricsRequest(); // \Omnismith\Sdk\Model\IngestMetricsRequest

try {
    $apiInstance->ingestEntityMetrics($id, $ingestMetricsRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->ingestEntityMetrics: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **ingestMetricsRequest** | [**\Omnismith\Sdk\Model\IngestMetricsRequest**](../Model/IngestMetricsRequest.md)|  | |

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

## `installMarketplaceBlueprint()`

```php
installMarketplaceBlueprint($id, $installMarketplaceBlueprintRequest)
```

Install a marketplace blueprint into a project

Installs a marketplace blueprint into the specified project context. Provisions all packaged templates, attributes, and relationships defined in the blueprint schema, and optionally populates sample demo entities. Automatically increments the installation count for the blueprint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 01912ecb-4654-7890-a1b2-c3d4e5f60003; // string | Unique UUID of the blueprint to install
$installMarketplaceBlueprintRequest = new \Omnismith\Sdk\Model\InstallMarketplaceBlueprintRequest(); // \Omnismith\Sdk\Model\InstallMarketplaceBlueprintRequest

try {
    $apiInstance->installMarketplaceBlueprint($id, $installMarketplaceBlueprintRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->installMarketplaceBlueprint: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID of the blueprint to install | |
| **installMarketplaceBlueprintRequest** | [**\Omnismith\Sdk\Model\InstallMarketplaceBlueprintRequest**](../Model/InstallMarketplaceBlueprintRequest.md)|  | |

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

## `listAttributeItems()`

```php
listAttributeItems($id): \Omnismith\Sdk\Model\ListAttributeItems200Response
```

List items of an attribute

Retrieves all selectable choice option items for a List-type (attribute_type = 2) attribute in ascending sort order. Each item contains its UUID, parent attribute ID, string value, and sort rank.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the List-type attribute

try {
    $result = $apiInstance->listAttributeItems($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listAttributeItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the List-type attribute | |

### Return type

[**\Omnismith\Sdk\Model\ListAttributeItems200Response**](../Model/ListAttributeItems200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAttributes()`

```php
listAttributes(): \Omnismith\Sdk\Model\ListAttributes200Response
```

List all attributes

Retrieves all schema attributes defined in the active project. Attributes represent the core schema building blocks across 4 kinds: Dimension (0), Metric (1), List (2), and Reference (3). Each attribute defines its storage data type (String: 0, Number: 1, Boolean: 2, Datetime: 3, Date: 4, File: 5, Image: 6, Markdown: 7), unique slug, optional description, associated templates, and reference configurations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listAttributes();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listAttributes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListAttributes200Response**](../Model/ListAttributes200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAuditLogs()`

```php
listAuditLogs($page, $limit, $sortBy, $sortDirection, $search, $eventType, $resourceType, $resourceId, $authorEmail, $start, $end): \Omnismith\Sdk\Model\ListAuditLogs200Response
```

List project audit logs

Returns an immutable, time-ordered audit trail of user and system events for the current project context.  ### Security & Authorization Restricted to authenticated users holding the Project Owner role.  ### Comprehensive Filtering & Search - `event_type`: Filter by single or comma-separated event types (e.g. `entity.created`, `entity.updated`, `entity.deleted`, `template.created`). - `resource_type`: Filter by domain target (e.g. `entity`, `template`, `attribute`, `project`). - `resource_id`: Filter by exact resource UUID. - `author_email`: Filter by the actor email address. - `start` and `end`: Date-time window bounding event occurrence (ISO 8601 or `YYYY-MM-DD HH:MM:SS`). - `search`: Text search across event types, resource types, resource IDs, author emails, and value summaries.  ### Pagination & Sorting Supports 1-indexed pagination (`page`, `limit` up to 100) and sorting by `occurred_at`, `event_type`, `resource_type`, `resource_id`, or `author_email` (`asc`/`desc`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page = 1; // int | 1-based page number for pagination
$limit = 20; // int | Number of audit log records per page (1-100)
$sortBy = occurred_at; // string | Field to sort audit log entries by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)
$search = entity.created; // string | Text search filter across event_type, resource_type, resource_id, author_email, and value
$eventType = entity.created; // string | Filter by single or comma-separated event types (e.g. \"entity.created,entity.updated\")
$resourceType = entity; // string | Filter by single or comma-separated resource types (e.g. \"entity,template,attribute\")
$resourceId = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Filter by exact resource unique identifier (UUID)
$authorEmail = demo@omnismith.io; // string | Filter by actor or author email address
$start = 2026-08-01T00:00:00Z; // \DateTime | Filter audit records occurring on or after this timestamp (ISO 8601 format)
$end = 2026-08-26T23:59:59Z; // \DateTime | Filter audit records occurring on or before this timestamp (ISO 8601 format)

try {
    $result = $apiInstance->listAuditLogs($page, $limit, $sortBy, $sortDirection, $search, $eventType, $resourceType, $resourceId, $authorEmail, $start, $end);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listAuditLogs: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page** | **int**| 1-based page number for pagination | [optional] [default to 1] |
| **limit** | **int**| Number of audit log records per page (1-100) | [optional] [default to 20] |
| **sortBy** | **string**| Field to sort audit log entries by | [optional] [default to &#39;occurred_at&#39;] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;desc&#39;] |
| **search** | **string**| Text search filter across event_type, resource_type, resource_id, author_email, and value | [optional] |
| **eventType** | **string**| Filter by single or comma-separated event types (e.g. \&quot;entity.created,entity.updated\&quot;) | [optional] |
| **resourceType** | **string**| Filter by single or comma-separated resource types (e.g. \&quot;entity,template,attribute\&quot;) | [optional] |
| **resourceId** | **string**| Filter by exact resource unique identifier (UUID) | [optional] |
| **authorEmail** | **string**| Filter by actor or author email address | [optional] |
| **start** | **\DateTime**| Filter audit records occurring on or after this timestamp (ISO 8601 format) | [optional] |
| **end** | **\DateTime**| Filter audit records occurring on or before this timestamp (ISO 8601 format) | [optional] |

### Return type

[**\Omnismith\Sdk\Model\ListAuditLogs200Response**](../Model/ListAuditLogs200Response.md)

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->listAutomations: ', $e->getMessage(), PHP_EOL;
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

## `listDashboardBlocks()`

```php
listDashboardBlocks($dashboardId): \Omnismith\Sdk\Model\ListDashboardBlocks200Response
```

List all blocks in a dashboard

Retrieves all visualization blocks mounted on a dashboard canvas, including widget types (stat KPI card, time-series chart, gauge meter, entity list), grid position coordinates (x, y, cols, rows), template filters, and aggregation configs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)

try {
    $result = $apiInstance->listDashboardBlocks($dashboardId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listDashboardBlocks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |

### Return type

[**\Omnismith\Sdk\Model\ListDashboardBlocks200Response**](../Model/ListDashboardBlocks200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDashboards()`

```php
listDashboards(): \Omnismith\Sdk\Model\ListDashboards200Response
```

List all dashboards

Retrieves all analytics dashboards configured within the authenticated project context, including dashboard metadata, layout settings, and visualization configurations.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listDashboards();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listDashboards: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListDashboards200Response**](../Model/ListDashboards200Response.md)

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listNotificationChannels();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listNotificationChannels: ', $e->getMessage(), PHP_EOL;
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

## `listTemplateEntityCounts()`

```php
listTemplateEntityCounts(): \Omnismith\Sdk\Model\ListTemplateEntityCounts200Response
```

List entity counts per template

Returns total entity record counts grouped by template UUID for all accessible templates in the current project context. Efficiently calculates counts and honors role-based resource access restrictions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listTemplateEntityCounts();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listTemplateEntityCounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListTemplateEntityCounts200Response**](../Model/ListTemplateEntityCounts200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplates()`

```php
listTemplates(): \Omnismith\Sdk\Model\ListTemplates200Response
```

List all templates

Retrieves all dynamic schema templates defined within the active project context. Templates represent content types grouping reusable attributes, establishing per-template default values, and organizing fields into visual layout groups for the UI workbench and entity forms.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listTemplates();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListTemplates200Response**](../Model/ListTemplates200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWorkspaces()`

```php
listWorkspaces(): \Omnismith\Sdk\Model\ListWorkspaces200Response
```

List all workspaces for current project

Retrieves all workspaces configured within the authenticated project context, including multi-pane layout structures (single, split-v, split-h, quad), view pane counts, sort ordering, and default workspace indicators for workbench navigation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listWorkspaces();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->listWorkspaces: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Omnismith\Sdk\Model\ListWorkspaces200Response**](../Model/ListWorkspaces200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchAttribute()`

```php
patchAttribute($id, $patchAttributeRequest)
```

Patch an attribute (granular partial update)

Applies partial modifications to an existing attribute without overwriting omitted fields. Allows independently changing name, description, slug, template associations, reference configuration, or transitioning data type. Lossless data type transition rules apply when updating data_type (Dimension only: Number(1)->String(0), Boolean(2)->String(0), Date(4)<->Datetime(3), Date(4)/Datetime(3)->String(0), String(0)<->Markdown(7)). Template associations merge and preserve restricted templates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to patch
$patchAttributeRequest = new \Omnismith\Sdk\Model\PatchAttributeRequest(); // \Omnismith\Sdk\Model\PatchAttributeRequest

try {
    $apiInstance->patchAttribute($id, $patchAttributeRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->patchAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to patch | |
| **patchAttributeRequest** | [**\Omnismith\Sdk\Model\PatchAttributeRequest**](../Model/PatchAttributeRequest.md)|  | |

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

## `patchTemplate()`

```php
patchTemplate($id, $patchTemplateRequest)
```

Patch a template (granular partial update)

Applies partial modifications to an existing template by UUID or slug without overwriting omitted fields. Allows modifying name, description, category, slug, attribute associations (with validated default values), or visual layout groups independently. Safely merges and preserves any restricted attributes.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to patch
$patchTemplateRequest = new \Omnismith\Sdk\Model\PatchTemplateRequest(); // \Omnismith\Sdk\Model\PatchTemplateRequest

try {
    $apiInstance->patchTemplate($id, $patchTemplateRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->patchTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to patch | |
| **patchTemplateRequest** | [**\Omnismith\Sdk\Model\PatchTemplateRequest**](../Model/PatchTemplateRequest.md)|  | |

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

## `resolveDashboardBlock()`

```php
resolveDashboardBlock($dashboardId, $blockId): \Omnismith\Sdk\Model\ResolvedBlockResponse
```

Resolve a dashboard block to its computed data

Executes the underlying data query for a dashboard block and returns computed real-time aggregated metrics and time-series telemetry. Returns a typed payload matching the block type: stat (matching entity count), gauge (current metric value, min/max bounds, progress percentage), chart (time-series data point series bucketed by time intervals with aggregation functions), or list (hydrated entity items with dynamic attributes).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID) to resolve and compute

try {
    $result = $apiInstance->resolveDashboardBlock($dashboardId, $blockId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->resolveDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) to resolve and compute | |

### Return type

[**\Omnismith\Sdk\Model\ResolvedBlockResponse**](../Model/ResolvedBlockResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchEntities()`

```php
searchEntities($templateId, $searchEntitiesRequest, $limit, $offset, $sortField, $sortDirection, $attributeKey): \Omnismith\Sdk\Model\SearchEntities200Response
```

Search entities with filtering, sorting, and pagination

Executes structured queries, full-text searches, and sorting across dynamic entities of a specified template schema.  ### Template Targeting (`template_id`) Accepts either a canonical template UUID (e.g. `018b2f1b-8c1a...`) or a human-readable template slug (e.g. `product_catalog`).  ### Structured Filters (`filters`) Filter conditions are specified in the request body as an array of filter objects: ```json [   {\"field\": \"status\", \"operator\": \"eq\", \"value\": \"018b2f1b-8c1a-75b3-8000-7f0000010020\"},   {\"field\": \"price\", \"operator\": \"gt\", \"value\": \"100\"},   {\"field\": \"name\", \"operator\": \"like\", \"value\": \"Pro\"} ] ``` - **`field`**: Target attribute UUID, attribute slug, or standard field (`id`, `created_at`, `updated_at`). - **`operator`**: Comparison operator: `eq` (equals), `neq` (not equals), `gt` (greater than), `lt` (less than), `like` (substring / trigram match), `not-like` (does not match), `empty` (is null or empty), `not-empty` (has value). - **`value`**: Target comparison value serialized as string.  ### Global Search (`global_search`) Performs accelerated full-text and GIN trigram matching across all string dimension attributes defined on the template.  ### Sorting & Pagination - **`sort_field`**: Attribute UUID, attribute slug, or standard entity fields (`id`, `created_at`, `updated_at`, `deleted_at`). - **`sort_direction`**: `asc` or `desc` (default: `asc` when `sort_field` is set, otherwise default sort is `created_at` DESC). - **`limit`** and **`offset`**: Bounded pagination (max 100 per page).  ### Attribute Key Formatting (`attribute_key`) Passing `attribute_key=\"slug\"` formats the returned `attribute_values` dictionary keys using human-readable attribute slugs instead of raw UUIDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$templateId = product_catalog; // string | Template UUID or human-readable template slug
$searchEntitiesRequest = new \Omnismith\Sdk\Model\SearchEntitiesRequest(); // \Omnismith\Sdk\Model\SearchEntitiesRequest
$limit = 50; // int | Maximum number of entity records to return (1-100)
$offset = 0; // int | Zero-based pagination offset
$sortField = created_at; // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by
$sortDirection = desc; // string | Sort direction: \"asc\" (ascending) or \"desc\" (descending)
$attributeKey = slug; // string | Format for attribute_values dictionary keys: \"id\" for attribute UUIDs or \"slug\" for human-readable attribute slugs

try {
    $result = $apiInstance->searchEntities($templateId, $searchEntitiesRequest, $limit, $offset, $sortField, $sortDirection, $attributeKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->searchEntities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **templateId** | **string**| Template UUID or human-readable template slug | |
| **searchEntitiesRequest** | [**\Omnismith\Sdk\Model\SearchEntitiesRequest**](../Model/SearchEntitiesRequest.md)|  | |
| **limit** | **int**| Maximum number of entity records to return (1-100) | [optional] [default to 50] |
| **offset** | **int**| Zero-based pagination offset | [optional] [default to 0] |
| **sortField** | **string**| Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [optional] |
| **sortDirection** | **string**| Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [optional] [default to &#39;asc&#39;] |
| **attributeKey** | **string**| Format for attribute_values dictionary keys: \&quot;id\&quot; for attribute UUIDs or \&quot;slug\&quot; for human-readable attribute slugs | [optional] [default to &#39;id&#39;] |

### Return type

[**\Omnismith\Sdk\Model\SearchEntities200Response**](../Model/SearchEntities200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchMarketplaceBlueprints()`

```php
searchMarketplaceBlueprints($search, $keywords, $limit, $offset, $sortBy, $sortDirection, $featured): \Omnismith\Sdk\Model\SearchMarketplaceBlueprints200Response
```

Search marketplace blueprints

Searches and lists public blueprints available in the marketplace catalog. Blueprints package reusable template schemas, attribute definitions, and sample data that users can install directly into their projects. Supports full-text search across titles and descriptions, keyword tag filtering, filtering by featured status, and sorting by creation date, install counts, or title.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$search = crm pipeline; // string | Free-text search filter across blueprint title and description
$keywords = crm,sales,leads; // string | Comma-separated keywords or tags to filter blueprints
$limit = 20; // int | Number of blueprint records to return per page (max 100)
$offset = 0; // int | Number of blueprint records to skip for pagination
$sortBy = installs; // string | Field to sort blueprint results by
$sortDirection = desc; // string | Sort direction order (ascending or descending)
$featured = true; // bool | Filter to return only curated and featured marketplace blueprints

try {
    $result = $apiInstance->searchMarketplaceBlueprints($search, $keywords, $limit, $offset, $sortBy, $sortDirection, $featured);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->searchMarketplaceBlueprints: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **search** | **string**| Free-text search filter across blueprint title and description | [optional] |
| **keywords** | **string**| Comma-separated keywords or tags to filter blueprints | [optional] |
| **limit** | **int**| Number of blueprint records to return per page (max 100) | [optional] [default to 20] |
| **offset** | **int**| Number of blueprint records to skip for pagination | [optional] [default to 0] |
| **sortBy** | **string**| Field to sort blueprint results by | [optional] [default to &#39;created_at&#39;] |
| **sortDirection** | **string**| Sort direction order (ascending or descending) | [optional] [default to &#39;desc&#39;] |
| **featured** | **bool**| Filter to return only curated and featured marketplace blueprints | [optional] |

### Return type

[**\Omnismith\Sdk\Model\SearchMarketplaceBlueprints200Response**](../Model/SearchMarketplaceBlueprints200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `setAttributeItems()`

```php
setAttributeItems($id, $setListItemsRequest)
```

Set list items for an attribute (replaces all existing items)

Atomically replaces all selectable option items for a List-type (attribute_type = 2) attribute. Existing list items for this attribute are removed and replaced with the provided array of items (with values, sort orders, and optional custom UUIDs). Returns HTTP 400 if the target attribute is not of List kind.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the List-type attribute
$setListItemsRequest = new \Omnismith\Sdk\Model\SetListItemsRequest(); // \Omnismith\Sdk\Model\SetListItemsRequest

try {
    $apiInstance->setAttributeItems($id, $setListItemsRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->setAttributeItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the List-type attribute | |
| **setListItemsRequest** | [**\Omnismith\Sdk\Model\SetListItemsRequest**](../Model/SetListItemsRequest.md)|  | |

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

## `setAttributeReferenceConfig()`

```php
setAttributeReferenceConfig($id, $setReferenceConfigRequest)
```

Set or update reference configuration for an attribute

Sets or updates the target template and display attribute for a Reference-type (attribute_type = 3) attribute. Enables relational linking and foreign entity display label resolution. Returns HTTP 400 if the target attribute is not of Reference kind.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the Reference attribute
$setReferenceConfigRequest = new \Omnismith\Sdk\Model\SetReferenceConfigRequest(); // \Omnismith\Sdk\Model\SetReferenceConfigRequest

try {
    $apiInstance->setAttributeReferenceConfig($id, $setReferenceConfigRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->setAttributeReferenceConfig: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the Reference attribute | |
| **setReferenceConfigRequest** | [**\Omnismith\Sdk\Model\SetReferenceConfigRequest**](../Model/SetReferenceConfigRequest.md)|  | |

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->testNotificationChannel: ', $e->getMessage(), PHP_EOL;
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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->toggleAutomation: ', $e->getMessage(), PHP_EOL;
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

## `updateAttribute()`

```php
updateAttribute($id, $updateAttributeRequest)
```

Update an attribute (full replacement)

Performs a full update of an existing attribute definition. Supports updating name, description, slug, template associations, reference configuration, and lossless data type transitions. Data type transitions are permitted only for Dimension (0) attributes and must follow lossless compatibility: Number(1) -> String(0), Boolean(2) -> String(0), Date(4) <-> Datetime(3), Date(4)/Datetime(3) -> String(0), and String(0) <-> Markdown(7). Non-lossless transitions or transitions on non-dimension attributes will return HTTP 422. Template associations preserve restricted templates the caller cannot see.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | UUID of the attribute to update
$updateAttributeRequest = new \Omnismith\Sdk\Model\UpdateAttributeRequest(); // \Omnismith\Sdk\Model\UpdateAttributeRequest

try {
    $apiInstance->updateAttribute($id, $updateAttributeRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateAttribute: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID of the attribute to update | |
| **updateAttributeRequest** | [**\Omnismith\Sdk\Model\UpdateAttributeRequest**](../Model/UpdateAttributeRequest.md)|  | |

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->updateAutomation: ', $e->getMessage(), PHP_EOL;
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

## `updateDashboard()`

```php
updateDashboard($id, $updateDashboardRequest)
```

Update a dashboard

Updates dashboard metadata including its display name, description, and canvas layout settings.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Dashboard unique identifier (UUID) to update
$updateDashboardRequest = new \Omnismith\Sdk\Model\UpdateDashboardRequest(); // \Omnismith\Sdk\Model\UpdateDashboardRequest | Dashboard update payload

try {
    $apiInstance->updateDashboard($id, $updateDashboardRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateDashboard: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Dashboard unique identifier (UUID) to update | |
| **updateDashboardRequest** | [**\Omnismith\Sdk\Model\UpdateDashboardRequest**](../Model/UpdateDashboardRequest.md)| Dashboard update payload | |

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

## `updateDashboardBlock()`

```php
updateDashboardBlock($dashboardId, $blockId, $updateDashboardBlockRequest)
```

Update a dashboard block

Updates the display title, grid placement (x, y, cols, rows), metric queries, time-series aggregation buckets, gauge bounds, or filtering rules of an existing visualization block.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dashboardId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Parent dashboard unique identifier (UUID)
$blockId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Dashboard block unique identifier (UUID) to update
$updateDashboardBlockRequest = new \Omnismith\Sdk\Model\UpdateDashboardBlockRequest(); // \Omnismith\Sdk\Model\UpdateDashboardBlockRequest | Dashboard block update payload

try {
    $apiInstance->updateDashboardBlock($dashboardId, $blockId, $updateDashboardBlockRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateDashboardBlock: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dashboardId** | **string**| Parent dashboard unique identifier (UUID) | |
| **blockId** | **string**| Dashboard block unique identifier (UUID) to update | |
| **updateDashboardBlockRequest** | [**\Omnismith\Sdk\Model\UpdateDashboardBlockRequest**](../Model/UpdateDashboardBlockRequest.md)| Dashboard block update payload | |

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

## `updateEntity()`

```php
updateEntity($id, $updateEntityRequest)
```

Update entity attribute values

Updates specific dynamic attribute values for an existing entity record.  ### Dynamic Attribute Values (`attribute_values`) Submit one or more attribute value updates. Each entry supports identifier resolution via: - `attribute_id`: Canonical attribute UUID - `attribute_slug`: Attribute slug identifier (e.g. `price`, `sku`, `status`)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value - **Dimension - Number**: Numeric string representation (e.g. `\"149.99\"`) - **Dimension - Boolean**: Boolean representation: `\"true\"`, `\"false\"`, `\"1\"`, or `\"0\"` - **Dimension - Date & Datetime**: Formatted as `YYYY-MM-DD` or `YYYY-MM-DD HH:MM:SS` / ISO 8601 `YYYY-MM-DDTHH:MM:SSZ` - **Dimension - File & Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined `ListItem` option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced `Entity`  ### Audit Trail & Metrics - Dimension updates are recorded in the append-only entity dimension change history log. - Metric attribute values submitted here are dispatched to the metric streaming pipeline for time-series aggregation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique entity identifier (UUID)
$updateEntityRequest = new \Omnismith\Sdk\Model\UpdateEntityRequest(); // \Omnismith\Sdk\Model\UpdateEntityRequest

try {
    $apiInstance->updateEntity($id, $updateEntityRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateEntity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique entity identifier (UUID) | |
| **updateEntityRequest** | [**\Omnismith\Sdk\Model\UpdateEntityRequest**](../Model/UpdateEntityRequest.md)|  | |

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


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
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
    echo 'Exception when calling MCPApi->updateNotificationChannel: ', $e->getMessage(), PHP_EOL;
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

## `updateTemplate()`

```php
updateTemplate($id, $updateTemplateRequest)
```

Update a template (full replacement)

Performs a full update of an existing template definition by UUID or slug. Replaces name, description, category, slug, attribute associations (with validated per-attribute default values), and UI layout groups. If the caller lacks permissions to certain restricted attributes, those restricted attributes are automatically preserved in the template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010010; // string | UUID or unique slug of the template to update
$updateTemplateRequest = new \Omnismith\Sdk\Model\UpdateTemplateRequest(); // \Omnismith\Sdk\Model\UpdateTemplateRequest

try {
    $apiInstance->updateTemplate($id, $updateTemplateRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| UUID or unique slug of the template to update | |
| **updateTemplateRequest** | [**\Omnismith\Sdk\Model\UpdateTemplateRequest**](../Model/UpdateTemplateRequest.md)|  | |

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

## `updateWorkspace()`

```php
updateWorkspace($id, $updateWorkspaceRequest)
```

Update workspace metadata and layout

Updates workspace attributes including display name, description, multi-pane layout arrangement (single, split-v, split-h, quad), sort order sequence, and default workspace status.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID) to update
$updateWorkspaceRequest = new \Omnismith\Sdk\Model\UpdateWorkspaceRequest(); // \Omnismith\Sdk\Model\UpdateWorkspaceRequest | Workspace update payload

try {
    $apiInstance->updateWorkspace($id, $updateWorkspaceRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) to update | |
| **updateWorkspaceRequest** | [**\Omnismith\Sdk\Model\UpdateWorkspaceRequest**](../Model/UpdateWorkspaceRequest.md)| Workspace update payload | |

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

## `updateWorkspaceView()`

```php
updateWorkspaceView($id, $viewId, $updateWorkspaceViewRequest)
```

Update workspace view / pane filters, sort, display mode, or columns

Updates the configuration of a specific workspace view pane, modifying its title, filtering rules, search query and mode, sorting preferences, presentation display mode (table or grid), column visibility lists, or pane display sequence.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\MCPApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b; // string | Workspace unique identifier (UUID)
$viewId = 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c; // string | Workspace view unique identifier (UUID) to update
$updateWorkspaceViewRequest = new \Omnismith\Sdk\Model\UpdateWorkspaceViewRequest(); // \Omnismith\Sdk\Model\UpdateWorkspaceViewRequest | Workspace view update payload

try {
    $apiInstance->updateWorkspaceView($id, $viewId, $updateWorkspaceViewRequest);
} catch (Exception $e) {
    echo 'Exception when calling MCPApi->updateWorkspaceView: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Workspace unique identifier (UUID) | |
| **viewId** | **string**| Workspace view unique identifier (UUID) to update | |
| **updateWorkspaceViewRequest** | [**\Omnismith\Sdk\Model\UpdateWorkspaceViewRequest**](../Model/UpdateWorkspaceViewRequest.md)| Workspace view update payload | |

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
