# PatchAttributeRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | New human-readable name for the attribute. | [optional]
**templateIds** | **string[]** | Updated array of template UUIDs to associate. When provided, replaces the template list while safely merging restricted templates. | [optional]
**description** | **string** | New descriptive text for the attribute. Pass null to clear. | [optional]
**referenceConfig** | [**\Omnismith\Sdk\Model\PatchAttributeRequestReferenceConfig**](PatchAttributeRequestReferenceConfig.md) |  | [optional]
**dataType** | **int** | Target data type for lossless transition on Dimension (0) attributes: Number(1)-&gt;String(0), Boolean(2)-&gt;String(0), Date(4)&lt;-&gt;Datetime(3), Date/Datetime-&gt;String(0), String(0)&lt;-&gt;Markdown(7). | [optional]
**slug** | **string** | New unique slug identifier within the project. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
