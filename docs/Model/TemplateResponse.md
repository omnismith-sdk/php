# TemplateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Template UUID | [optional]
**slug** | **string** | Unique template slug identifier | [optional]
**name** | **string** | Human-readable template name | [optional]
**description** | **string** | Template description | [optional]
**category** | **string** | Template category for UI grouping | [optional]
**attributeIds** | **string[]** | Flat list of associated attribute UUIDs | [optional]
**attributes** | [**\Omnismith\Sdk\Model\TemplateResponseAttributesInner[]**](TemplateResponseAttributesInner.md) | Template attributes with their per-template default values. | [optional]
**groups** | [**\Omnismith\Sdk\Model\TemplateGroupResponse[]**](TemplateGroupResponse.md) | Ordered attribute groups for organizing template fields into visual UI sections. | [optional]
**createdAt** | **\DateTime** | Creation timestamp | [optional]
**updatedAt** | **\DateTime** | Last update timestamp | [optional]
**deletedAt** | **\DateTime** | Deletion timestamp if soft-deleted | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
