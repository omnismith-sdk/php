# BiSchemaField

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**templateId** | **string** | Template UUID to which this field belongs | [optional]
**templateName** | **string** | Display name of the template schema | [optional]
**columnName** | **string** | Sanitized SQL-friendly column identifier for BI connectors | [optional]
**label** | **string** | Human-readable column header label | [optional]
**source** | **string** | Field origin (\&quot;system\&quot; for metadata columns, \&quot;attribute\&quot; for dynamic template attributes) | [optional]
**attributeId** | **string** | Attribute definition UUID if source is attribute | [optional]
**attributeName** | **string** | Display name of the attribute definition | [optional]
**attributeType** | **string** | Kind of dynamic attribute (dimension, metric, list, reference) | [optional]
**dataType** | **string** | Canonical data type mapping for BI tooling (string, number, boolean, datetime, date) | [optional]
**referenceTargetTemplateId** | **string** | Target template UUID if this is a reference attribute | [optional]
**referenceTargetAttributeId** | **string** | Target display attribute UUID if this is a reference attribute | [optional]
**listOptions** | [**\Omnismith\Sdk\Model\BiFieldOption[]**](BiFieldOption.md) | Allowed selectable options if this is a list attribute | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
