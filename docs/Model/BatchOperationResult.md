# BatchOperationResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**index** | **int** | Position of this operation in the submitted array. | [optional]
**op** | **string** | The operation that was attempted. | [optional]
**id** | **string** | Entity the operation acted on. For a successful create this is the newly generated identifier. Null when a create failed before an identifier existed. | [optional]
**status** | **string** | Outcome of this operation. | [optional]
**error** | [**\Omnismith\Sdk\Model\ErrorResponse**](ErrorResponse.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
