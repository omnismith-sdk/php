# EntityActionAvailability

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Action UUID |
**slug** | **string** | The identifier to execute it with: &#x60;POST /entities/{id}/actions/{slug}&#x60; |
**name** | **string** |  |
**description** | **string** |  |
**icon** | **string** | Material icon name |
**available** | **bool** | Whether the precondition holds for the record&#39;s current values. Executing an unavailable action returns 409. |
**unavailableReason** | **string** | Why the action cannot run now, naming the attribute, the expectation and the current value. Null when available. |
**fields** | [**\Omnismith\Sdk\Model\EntityActionAvailableField[]**](EntityActionAvailableField.md) | Values to submit, in dialog order |
**presets** | [**\Omnismith\Sdk\Model\EntityActionAvailablePreset[]**](EntityActionAvailablePreset.md) | Values the action writes on its own |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
