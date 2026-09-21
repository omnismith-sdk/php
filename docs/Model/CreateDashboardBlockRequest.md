# CreateDashboardBlockRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | Block visualization type: stat (single KPI counter of matching entities), chart (time-series telemetry multi-line graph aggregating metric values over time), gauge (radial threshold meter displaying metric aggregate within bounds), list (filtered and sorted entity data table), aggregate (entities grouped by one or more fields and reduced per group — a \&quot;count by status\&quot; or \&quot;sum of MRR by tier\&quot; table). |
**title** | **string** | Header title displayed on the dashboard widget card (e.g., \&quot;CPU Utilization — Time Series\&quot;, \&quot;Total Servers\&quot;, \&quot;Peak CPU Utilization\&quot;). |
**config** | [**\Omnismith\Sdk\Model\CreateDashboardBlockRequestConfig**](CreateDashboardBlockRequestConfig.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
