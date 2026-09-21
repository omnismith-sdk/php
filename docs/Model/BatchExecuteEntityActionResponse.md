# BatchExecuteEntityActionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**atomic** | **bool** | Whether the batch ran as a single transaction. |
**total** | **int** | Number of records submitted. |
**executed** | **int** | Records the action ran on. |
**preconditionFailed** | **int** | Records skipped because the precondition did not hold. |
**ruleViolated** | **int** | Records refused by a template rule. |
**failed** | **int** | Records refused for any other reason. |
**results** | [**\Omnismith\Sdk\Model\EntityActionOutcome[]**](EntityActionOutcome.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
