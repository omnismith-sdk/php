# UpdateNotificationChannelRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Updated display name of the notification channel | [optional]
**credentials** | [**\Omnismith\Sdk\Model\UpdateNotificationChannelRequestCredentials**](UpdateNotificationChannelRequestCredentials.md) |  | [optional]
**rateLimitPerMinute** | **int** | Maximum messages the channel sends per clock minute, across all automations and records; sends over it fail the action (recorded in the execution history) instead of reaching the destination. Omit to keep the current limit. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
