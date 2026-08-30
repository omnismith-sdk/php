# CreateEntityRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**templateId** | **string** | Template UUID to instantiate (mutually exclusive with template_slug) | [optional]
**attributeValues** | [**\Omnismith\Sdk\Model\CreateEntityRequestAttributeValuesInner[]**](CreateEntityRequestAttributeValuesInner.md) | Initial attribute values for dimensions, lists, references, and initial metrics | [optional]
**id** | **string** | Optional client-assigned UUIDv7 identifier for the entity record. If omitted, a UUIDv7 is automatically generated. | [optional]
**templateSlug** | **string** | Template slug identifier to instantiate (mutually exclusive with template_id) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
