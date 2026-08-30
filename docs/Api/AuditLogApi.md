# Omnismith\Sdk\AuditLogApi

AuditLog

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listAuditLogs()**](AuditLogApi.md#listAuditLogs) | **GET** /audit-logs | List project audit logs |


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


$apiInstance = new Omnismith\Sdk\Api\AuditLogApi(
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
    echo 'Exception when calling AuditLogApi->listAuditLogs: ', $e->getMessage(), PHP_EOL;
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
