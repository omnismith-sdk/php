# UpdateAutomationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Updated display name of the automation rule | [optional]
**description** | **string** | Updated description of the automation rule | [optional]
**trigger** | [**\Omnismith\Sdk\Model\UpdateAutomationRequestTrigger**](UpdateAutomationRequestTrigger.md) |  | [optional]
**conditions** | [**\Omnismith\Sdk\Model\UpdateAutomationRequestConditionsInner[]**](UpdateAutomationRequestConditionsInner.md) | Updated array of condition criteria evaluated against entity state | [optional]
**actions** | [**\Omnismith\Sdk\Model\UpdateAutomationRequestActionsInner[]**](UpdateAutomationRequestActionsInner.md) | Updated list of dispatch actions | [optional]
**cooldownSeconds** | **int** | Updated cooldown throttle duration in seconds | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
