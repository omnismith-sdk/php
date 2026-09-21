# EntityResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique entity identifier (UUIDv7) | [optional]
**templateId** | **string** | UUID of the template schema to which this entity conforms | [optional]
**templateSlug** | **string** | Human-readable slug of the template schema | [optional]
**createdAt** | **\DateTime** | Record creation timestamp in ISO 8601 format | [optional]
**updatedAt** | **\DateTime** | Last modification timestamp in ISO 8601 format | [optional]
**attributeValues** | [**\Omnismith\Sdk\Model\EntityResponseAttributeValues**](EntityResponseAttributeValues.md) |  | [optional]
**listItemIds** | **array<string,string>** | Compact mode only: list option ids behind the labels shown in &#x60;attribute_values&#x60;, keyed like &#x60;attribute_values&#x60;. Use these ids when writing the attribute or filtering by it — writes and filters take ids, not labels. Absent when &#x60;verbose&#x3D;true&#x60; (the items carry &#x60;value&#x60;). | [optional]
**referenceEntityIds** | **array<string,string>** | Compact mode only: referenced entity ids behind the labels shown in &#x60;attribute_values&#x60;, keyed like &#x60;attribute_values&#x60;. Pass one to &#x60;GET /entities/{id}&#x60; to load the referenced record, or use it when writing or filtering the attribute. Absent when &#x60;verbose&#x3D;true&#x60;. | [optional]
**fileIds** | **array<string,string>** | Compact mode only: file attachment ids behind the filenames shown in &#x60;attribute_values&#x60;, keyed like &#x60;attribute_values&#x60;. Absent when &#x60;verbose&#x3D;true&#x60;. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
