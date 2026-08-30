# UpdateTemplateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributes** | [**\Omnismith\Sdk\Model\TemplateAttributeInput[]**](TemplateAttributeInput.md) | Structured template attributes with optional per-template default values. Preferred over flat attribute_ids. | [optional]
**groups** | [**\Omnismith\Sdk\Model\TemplateGroupInput[]**](TemplateGroupInput.md) | Ordered attribute groups for organizing template fields into visual UI sections. | [optional]
**name** | **string** | Updated human-readable name of the template. |
**description** | **string** | Updated description of the template. | [optional]
**category** | **string** | Updated category tag for grouping in navigation. | [optional]
**attributeIds** | **string[]** | Flat list of attribute UUIDs to associate without custom defaults. | [optional]
**attributeSlugs** | **string[]** | Flat list of attribute slugs to associate with this template. | [optional]
**slug** | **string** | Updated unique slug identifier within the project. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
