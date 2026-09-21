# BatchWriteEntitiesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**operations** | [**\Omnismith\Sdk\Model\BatchOperationInput[]**](BatchOperationInput.md) | Operations applied in the order given, at most 100 per call. |
**atomic** | **bool** | When false (the default) every operation is attempted and failures are reported per index. When true the batch runs in a single transaction and the first failure rolls all of it back. Atomic batches reject metric values, which are published outside the transaction and cannot be rolled back. | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
