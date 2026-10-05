# PreviewInboundMapping200ResponseItemsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**index** | **int** | Position in the payload&#39;s &#x60;items&#x60; list; 0 without one |
**externalKey** | **string** |  |
**action** | **string** | What a delivery would do with this record; null when the record fails before that is known |
**entityId** | **string** | The record an update would change |
**attributes** | **array<string,mixed>** | Values keyed as in the mapping: a string, null to clear, or &#x60;{value, updated_at}&#x60; for a timed value |
**error** | **array<string,mixed>** | The error body a real delivery would meet for this record |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
