# CreateAutomationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Descriptive display name of the automation rule |
**description** | **string** | Optional summary describing the purpose and behavior of the automation | [optional]
**trigger** | [**\Omnismith\Sdk\Model\CreateAutomationRequestTrigger**](CreateAutomationRequestTrigger.md) |  |
**conditions** | [**\Omnismith\Sdk\Model\CreateAutomationRequestConditionsInner[]**](CreateAutomationRequestConditionsInner.md) | Condition expressions that must all evaluate to true against the entity for actions to run |
**actions** | [**\Omnismith\Sdk\Model\CreateAutomationRequestActionsInner[]**](CreateAutomationRequestActionsInner.md) | List of dispatch actions to execute when trigger and conditions are met |
**cooldownSeconds** | **int** | Minimum throttle cooldown window in seconds between firings for the same entity | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
