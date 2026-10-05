# AutomationTrigger

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | What fires the automation: a record event (&#x60;on_entity_created&#x60;, &#x60;on_entity_updated&#x60;, &#x60;on_attribute_changed&#x60;, &#x60;on_action_executed&#x60;) or the clock (&#x60;schedule&#x60;, &#x60;date_reached&#x60;, &#x60;no_change_within&#x60;). |
**templateId** | **string** | Template id the trigger watches. Required for &#x60;date_reached&#x60; and &#x60;no_change_within&#x60;; optional for record events (none &#x3D; every template) and for &#x60;schedule&#x60; (none &#x3D; one run without a record). | [optional]
**attributeId** | **string** | Attribute id of the template; required for &#x60;on_attribute_changed&#x60;, &#x60;date_reached&#x60; (a date or datetime attribute) and &#x60;no_change_within&#x60; (the watched attribute; not a metric), absent otherwise. | [optional]
**actionId** | **string** | Entity action id; required for &#x60;on_action_executed&#x60;, absent otherwise. | [optional]
**cron** | **string** | &#x60;schedule&#x60; only: a 5-field cron expression (minute hour day-of-month month day-of-week), read in &#x60;timezone&#x60;. Runs at least 5 minutes apart. | [optional]
**timezone** | **string** | Time-based triggers only: the IANA timezone their times are read in, e.g. &#x60;Europe/Berlin&#x60;. | [optional]
**delayMinutes** | **int** | &#x60;no_change_within&#x60; only: how long the watched attribute must stay unchanged, 5 to 129600 minutes (90 days). Also accepted as &#x60;delay_minutes&#x60;. | [optional]
**offsetMinutes** | **int** | &#x60;date_reached&#x60; only: signed whole minutes from the date, negative for before it; at most 527040 (366 days) either way. Also accepted as &#x60;offset_minutes&#x60;. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
