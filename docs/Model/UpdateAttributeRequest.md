# UpdateAttributeRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Updated human-readable name of the attribute. |
**templateIds** | **string[]** | Complete list of template UUIDs associated with this attribute. Replaces current template associations while preserving restricted templates. | [optional]
**description** | **string** | Updated description of the attribute. | [optional]
**referenceConfig** | [**\Omnismith\Sdk\Model\PatchAttributeRequestReferenceConfig**](PatchAttributeRequestReferenceConfig.md) |  | [optional]
**dataType** | **int** | Target data type for lossless transition on Dimension (0) attributes: Number(1)-&gt;String(0), Boolean(2)-&gt;String(0), Date(4)&lt;-&gt;Datetime(3), Date/Datetime-&gt;String(0), String(0)&lt;-&gt;Markdown(7). | [optional]
**slug** | **string** | Updated unique slug identifier within the project. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
