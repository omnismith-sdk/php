# AttributeResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Attribute UUID | [optional]
**slug** | **string** | Unique slug identifier within the project | [optional]
**name** | **string** | Human-readable attribute name | [optional]
**description** | **string** | Attribute description | [optional]
**attributeType** | **int** | 0: Dimension, 1: Metric, 2: List, 3: Reference | [optional]
**dataType** | **int** | 0: String, 1: Number, 2: Boolean, 3: Datetime, 4: Date, 5: File, 6: Image, 7: Markdown | [optional]
**templateIds** | **string[]** | Array of template UUIDs associated with this attribute | [optional]
**referenceConfig** | [**\Omnismith\Sdk\Model\AttributeResponseReferenceConfig**](AttributeResponseReferenceConfig.md) |  | [optional]
**createdAt** | **\DateTime** | Creation timestamp | [optional]
**updatedAt** | **\DateTime** | Last update timestamp | [optional]
**deletedAt** | **\DateTime** | Deletion timestamp if soft-deleted | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
