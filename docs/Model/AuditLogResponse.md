# AuditLogResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**eventId** | **string** | Unique audit event identifier (UUIDv7) | [optional]
**occurredAt** | **\DateTime** | Event occurrence timestamp in ISO 8601 format | [optional]
**eventType** | **string** | Action or event identifier (e.g. entity.created, entity.updated, entity.deleted, template.created) | [optional]
**resourceType** | **string** | Target domain resource type (entity, template, attribute, project) | [optional]
**resourceId** | **string** | Target resource identifier (UUID) | [optional]
**value** | **string** | Summary description or serialized payload of the mutation | [optional]
**authorEmail** | **string** | Email of the authenticated user who initiated the action | [optional]
**correlationId** | **string** | Distributed tracing correlation identifier | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
