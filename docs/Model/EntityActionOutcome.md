# EntityActionOutcome

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**entityId** | **string** | OpenAPI schema for the outcome of the action on one record of a batch. |
**status** | **string** | &#x60;executed&#x60; — written as the receipt says. &#x60;precondition_failed&#x60; — the record was not in the state the action needs (&#x60;error.reason&#x60; says why). &#x60;rule_violated&#x60; — a template rule refused the write (&#x60;error.errors&#x60; keyed by &#x60;attributes.&lt;slug&gt;&#x60;). &#x60;failed&#x60; — any other refusal: unknown record, no permission, a value failing its type. |
**receipt** | [**\Omnismith\Sdk\Model\ExecuteEntityActionResponse**](ExecuteEntityActionResponse.md) |  |
**error** | [**\Omnismith\Sdk\Model\ErrorResponse**](ErrorResponse.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
