# AutomationExecutionResponseActionResultsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actionIndex** | **int** | Zero-based index of the action in the automation definition | [optional]
**success** | **bool** | Whether this specific action executed successfully | [optional]
**errorMessage** | **string** | Error message if action execution failed | [optional]
**executedAt** | **\DateTime** | Timestamp of action dispatch | [optional]
**details** | **object** | What the action reported beyond success. An &#x60;http_request&#x60; action reports &#x60;status_code&#x60;, &#x60;written&#x60; (the attributes its response mapping wrote) and &#x60;response_excerpt&#x60; (the first 2 KB of the response body). Null for actions that report nothing. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
