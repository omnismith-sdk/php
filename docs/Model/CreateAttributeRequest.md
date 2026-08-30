# CreateAttributeRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Human-readable name of the attribute. |
**attributeType** | **int** | Attribute kind. 0: Dimension (standard field), 1: Metric (time-series observation), 2: List (enumerated choice option), 3: Reference (foreign entity pointer). |
**dataType** | **int** | Storage data type. 0: String, 1: Number, 2: Boolean, 3: Datetime, 4: Date, 5: File, 6: Image, 7: Markdown. |
**templateIds** | **string[]** | Optional array of template UUIDs to immediately associate this attribute with. | [optional]
**description** | **string** | Optional descriptive summary of the attribute and its business purpose. | [optional]
**referenceConfig** | [**\Omnismith\Sdk\Model\CreateAttributeRequestReferenceConfig**](CreateAttributeRequestReferenceConfig.md) |  | [optional]
**id** | **string** | Optional explicit client-generated UUIDv7. If omitted, a UUIDv7 is automatically generated. | [optional]
**slug** | **string** | Unique slug identifier within the project (letters, numbers, underscores). If omitted, generated automatically from name. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
