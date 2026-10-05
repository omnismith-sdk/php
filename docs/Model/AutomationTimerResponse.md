# AutomationTimerResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Timer UUID. There is at most one pending timer per automation, record and kind, so re-arming keeps the id. |
**automationId** | **string** | Automation the timer belongs to |
**automationName** | **string** | Name of that automation |
**entityId** | **string** | Record the timer is about; null for a timer that belongs to no record (a schedule without a template) |
**kind** | **string** | What the timer is for: the next slot of a schedule, a date attribute reaching its moment, or a \&quot;no change within\&quot; deadline |
**dueAt** | **\DateTime** | When the timer fires (UTC). It fires within about 30 seconds of this moment; one that came due while the service was down fires once, late. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
