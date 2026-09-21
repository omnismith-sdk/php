# Omnismith\Sdk\AuditLogApi

AuditLog

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listAuditLogs()**](AuditLogApi.md#listAuditLogs) | **GET** /audit-logs | List project audit logs |


## `listAuditLogs()`

```php
listAuditLogs($xOmnismithProjectId, $page, $limit, $sortBy, $sortDirection, $search, $eventType, $resourceType, $resourceId, $authorEmail, $start, $end): \Omnismith\Sdk\Model\ListAuditLogs200Response
```

List project audit logs

Returns an immutable, time-ordered audit trail of user and system events for the current project context. Restricted to authenticated users holding the Project Owner role. Returns paginated `items`, each an event (`event_type`, `resource_type`/`resource_id`, `author_email`, a `value` summary, `occurred_at`) plus `total` matching records.

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
$xOmnismithProjectId = 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d; // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential's `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time.
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
    $result = $apiInstance->listAuditLogs($xOmnismithProjectId, $page, $limit, $sortBy, $sortDirection, $search, $eventType, $resourceType, $resourceId, $authorEmail, $start, $end);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuditLogApi->listAuditLogs: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **xOmnismithProjectId** | **string**| The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [optional] |
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
