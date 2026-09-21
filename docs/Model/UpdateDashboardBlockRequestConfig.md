# UpdateDashboardBlockRequestConfig

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**templateId** | **string** | UUID of the entity template | [optional]
**metricAttributeId** | **string** | UUID of the metric attribute | [optional]
**timeWindow** | **int** | Time range query window in seconds for historical telemetry (e.g. 3600, 10800, 21600, 43200, 86400, 604800, 2592000) | [optional]
**bucketWidth** | **string** | Time bucket interval for chart aggregation (e.g. \&quot;1 min\&quot;, \&quot;5 min\&quot;, \&quot;1 hour\&quot;, \&quot;1 day\&quot;) | [optional]
**aggregate** | **string** | Aggregation function (\&quot;avg\&quot;, \&quot;sum\&quot;, \&quot;min\&quot;, \&quot;max\&quot;, \&quot;first\&quot;, \&quot;last\&quot;, \&quot;count\&quot;) | [optional]
**entityLimit** | **int** | Maximum entity series count (1-50) | [optional]
**min** | **float** | Minimum scale value for gauge blocks | [optional]
**max** | **float** | Maximum scale value for gauge blocks | [optional]
**unit** | **string** | Unit suffix for gauge blocks (e.g. \&quot;%\&quot;) | [optional]
**startColor** | **string** | Start gradient color | [optional]
**midColor** | **string** | Middle gradient color | [optional]
**endColor** | **string** | End gradient color | [optional]
**limit** | **int** | Entity limit for list blocks | [optional]
**sort** | **object** | Sort config object for list blocks | [optional]
**visibleAttributes** | **string[]** | List block visible attribute IDs | [optional]
**groupBy** | **string[]** | Aggregate block group-by fields, at most 3 | [optional]
**aggregations** | [**\Omnismith\Sdk\Model\UpdateDashboardBlockRequestConfigAggregationsInner[]**](UpdateDashboardBlockRequestConfigAggregationsInner.md) | Aggregate block reduces (1-10 entries) | [optional]
**filters** | **object[]** | Entity filter rules | [optional]
**x** | **int** | Horizontal grid column (0..11 on 12-column grid) | [optional]
**y** | **int** | Vertical grid row (0..N) | [optional]
**cols** | **int** | Block width in columns (1..12) | [optional]
**rows** | **int** | Block height in rows (1..N) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
