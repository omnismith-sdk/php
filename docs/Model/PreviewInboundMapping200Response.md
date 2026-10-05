# PreviewInboundMapping200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**mode** | **string** |  |
**matched** | **bool** | Whether the &#x60;match&#x60; conditions hold. When they do not, a real delivery is acknowledged and skipped. |
**skipped** | **string** | &#x60;match&#x60; when the conditions do not hold, &#x60;no_items&#x60; when the &#x60;items&#x60; list is empty; null when records would be written. |
**items** | [**\Omnismith\Sdk\Model\PreviewInboundMapping200ResponseItemsInner[]**](PreviewInboundMapping200ResponseItemsInner.md) |  |
**errors** | **array<string,string[]>** | Every record error by field, &#x60;items[i].attributes.&lt;slug&gt;&#x60; &#x3D;&gt; messages |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
