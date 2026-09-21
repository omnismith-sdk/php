# BatchWriteEntitiesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**atomic** | **bool** | Whether the batch ran as a single transaction. | [optional]
**total** | **int** | Number of operations submitted. | [optional]
**created** | **int** | Number of entities created. | [optional]
**updated** | **int** | Number of entities updated. | [optional]
**replaced** | **int** | Number of entities replaced. | [optional]
**deleted** | **int** | Number of entities soft-deleted. | [optional]
**failed** | **int** | Number of operations that failed. Non-zero means the batch partially applied. | [optional]
**results** | [**\Omnismith\Sdk\Model\BatchOperationResult[]**](BatchOperationResult.md) | One entry per submitted operation, in the submitted order. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
