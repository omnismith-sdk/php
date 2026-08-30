# PatchTemplateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributes** | [**\Omnismith\Sdk\Model\TemplateAttributeInput[]**](TemplateAttributeInput.md) | Structured template attributes with optional per-template default values. If provided, replaces attribute associations. | [optional]
**groups** | [**\Omnismith\Sdk\Model\TemplateGroupInput[]**](TemplateGroupInput.md) | Ordered attribute groups for organizing template fields into visual UI sections. | [optional]
**name** | **string** | New human-readable name of the template. | [optional]
**description** | **string** | New description for the template. | [optional]
**category** | **string** | New category tag for navigation grouping. | [optional]
**attributeIds** | **string[]** | Flat list of attribute UUIDs to associate. | [optional]
**attributeSlugs** | **string[]** | Flat list of attribute slugs to associate. | [optional]
**slug** | **string** | New unique slug identifier within the project. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
