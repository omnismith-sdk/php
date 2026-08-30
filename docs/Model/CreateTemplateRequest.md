# CreateTemplateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributes** | [**\Omnismith\Sdk\Model\TemplateAttributeInput[]**](TemplateAttributeInput.md) | Structured list of template attributes with optional per-template default values. Preferred over flat attribute_ids. | [optional]
**groups** | [**\Omnismith\Sdk\Model\TemplateGroupInput[]**](TemplateGroupInput.md) | Optional ordered attribute groups for organizing template fields into visual UI sections (1 or 2 columns). | [optional]
**name** | **string** | Human-readable name of the template. |
**description** | **string** | Optional description of what entities conforming to this template represent. | [optional]
**category** | **string** | Optional category tag for grouping templates in navigation. | [optional]
**attributeIds** | **string[]** | Flat list of attribute UUIDs to associate with this template without custom default values. | [optional]
**attributeSlugs** | **string[]** | Flat list of attribute slugs to associate with this template by slug resolution. | [optional]
**id** | **string** | Optional explicit client-generated UUIDv7. Generated automatically if omitted. | [optional]
**slug** | **string** | Unique template slug identifier (letters, numbers, underscores). Auto-generated from name if omitted. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
