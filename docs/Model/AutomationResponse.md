# AutomationResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique automation UUID | [optional]
**name** | **string** | Name of the automation rule | [optional]
**description** | **string** | Optional description of the automation rule | [optional]
**isEnabled** | **bool** | Whether the automation is currently active and listening for events | [optional]
**trigger** | [**\Omnismith\Sdk\Model\AutomationResponseTrigger**](AutomationResponseTrigger.md) |  | [optional]
**conditions** | [**\Omnismith\Sdk\Model\AutomationResponseConditionsInner[]**](AutomationResponseConditionsInner.md) | Condition expressions that must all evaluate to true to execute actions | [optional]
**actions** | [**\Omnismith\Sdk\Model\AutomationResponseActionsInner[]**](AutomationResponseActionsInner.md) | Actions dispatched when conditions evaluate to true | [optional]
**cooldownSeconds** | **int** | Minimum cooldown seconds between trigger firings for the same entity | [optional]
**lastTriggeredAt** | **\DateTime** | Timestamp when this automation last fired | [optional]
**createdAt** | **\DateTime** | Creation timestamp | [optional]
**updatedAt** | **\DateTime** | Last update timestamp | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
