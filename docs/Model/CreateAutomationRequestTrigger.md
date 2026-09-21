# CreateAutomationRequestTrigger

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | Trigger event type. &#x60;on_action_executed&#x60; fires when the named entity action runs on a record, whether or not the write changed anything. |
**templateId** | **string** | Template UUID to listen for events on | [optional]
**attributeId** | **string** | Attribute UUID for attribute change triggers | [optional]
**actionId** | **string** | Entity action UUID; required for &#x60;on_action_executed&#x60;, must be null otherwise | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
