# AutomationExecutionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique execution record UUID | [optional]
**automationId** | **string** | Associated automation rule UUID | [optional]
**entityId** | **string** | UUID of the entity that triggered the execution | [optional]
**triggeredAt** | **\DateTime** | Timestamp when the trigger event was evaluated | [optional]
**completedAt** | **\DateTime** | Timestamp when all actions completed execution | [optional]
**status** | **string** | Overall execution outcome status | [optional]
**actionResults** | [**\Omnismith\Sdk\Model\AutomationExecutionResponseActionResultsInner[]**](AutomationExecutionResponseActionResultsInner.md) | Individual action execution outcomes | [optional]
**errorMessage** | **string** | Top-level error message if execution failed | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
