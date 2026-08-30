# TemplateAttributeInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributeId** | **string** | Attribute UUID. Specify either attribute_id or attribute_slug. | [optional]
**attributeSlug** | **string** | Attribute unique slug. Specify either attribute_id or attribute_slug. | [optional]
**defaultValue** | **string** | Default value applied to new entities when omitted. For List attributes, must be a valid list item UUID. For Reference attributes, a target entity UUID. For Metric/Number, a numeric string. For Boolean, \&quot;true\&quot; or \&quot;false\&quot;. For Date/Datetime, an ISO timestamp string. For File/Image, defaults are unsupported. Null means no default. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
