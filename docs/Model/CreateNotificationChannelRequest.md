# CreateNotificationChannelRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | Channel delivery type (telegram, webhook, push) |
**name** | **string** | Display name of the notification channel |
**credentials** | [**\Omnismith\Sdk\Model\CreateNotificationChannelRequestCredentials**](CreateNotificationChannelRequestCredentials.md) |  |
**rateLimitPerMinute** | **int** | Maximum messages the channel sends per clock minute, across all automations and records; sends over it fail the action (recorded in the execution history) instead of reaching the destination. Defaults to 20, Telegram&#39;s limit for one group. | [optional] [default to 20]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
