# EntityActionAvailableField

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributeId** | **string** |  |
**slug** | **string** | Attribute slug; the key to use in &#x60;values&#x60;. Null for an attribute without a slug — use &#x60;attribute_id&#x60; then. |
**name** | **string** |  |
**attributeType** | **int** | 0: Dimension, 2: List, 3: Reference (metrics are never action fields) |
**dataType** | **int** | 0: String, 1: Number, 2: Boolean, 3: Datetime, 4: Date, 5: File, 6: Image, 7: Markdown |
**required** | **bool** | Execution refuses an empty value with 422 keyed by &#x60;attributes.&lt;slug&gt;&#x60; |
**hint** | **string** |  |
**listItems** | [**\Omnismith\Sdk\Model\EntityActionAvailableFieldListItemsInner[]**](EntityActionAvailableFieldListItemsInner.md) | The choices of a list attribute; the value to send is the item &#x60;id&#x60;. Empty for other attribute types. |
**referenceConfig** | [**\Omnismith\Sdk\Model\EntityActionAvailableFieldReferenceConfig**](EntityActionAvailableFieldReferenceConfig.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
