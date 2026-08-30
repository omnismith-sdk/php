# EntityResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique entity identifier (UUIDv7) | [optional]
**templateId** | **string** | UUID of the template schema to which this entity conforms | [optional]
**templateSlug** | **string** | Human-readable slug of the template schema | [optional]
**createdAt** | **\DateTime** | Record creation timestamp in ISO 8601 format | [optional]
**updatedAt** | **\DateTime** | Last modification timestamp in ISO 8601 format | [optional]
**attributeValues** | [**array<string,\Omnismith\Sdk\Model\EntityAttributeValue>**](EntityAttributeValue.md) | Dictionary of attribute values keyed by attribute UUID or attribute slug (controlled by the attribute_key query parameter) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
