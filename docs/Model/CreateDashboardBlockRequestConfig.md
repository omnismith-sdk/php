# CreateDashboardBlockRequestConfig

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**templateId** | **string** | UUID of the entity template serving as the data source (required for all block types). | [optional]
**metricAttributeId** | **string** | UUID of the metric attribute to aggregate/plot (required for chart and metric gauge blocks). | [optional]
**timeWindow** | **int** | Time range query window in seconds for historical telemetry. CRITICAL for chart and time-series gauge blocks to query Entity Log data points. Presets: 3600 (1 hour), 10800 (3 hours), 21600 (6 hours), 43200 (12 hours), 86400 (24 hours / 1 day, recommended default), 604800 (7 days / 1 week), 2592000 (30 days / 1 month). | [optional] [default to 86400]
**bucketWidth** | **string** | Time bucket interval for chart data aggregation. Standard values: \&quot;1 min\&quot;, \&quot;5 min\&quot;, \&quot;10 min\&quot;, \&quot;15 min\&quot;, \&quot;1 hour\&quot; (default), \&quot;6 hours\&quot;, \&quot;12 hours\&quot;, \&quot;1 day\&quot;, \&quot;1 week\&quot;, \&quot;1 month\&quot;. | [optional] [default to '1 hour']
**aggregate** | **string** | Aggregation function for telemetry metric points: \&quot;avg\&quot; (default for gauge/chart), \&quot;sum\&quot;, \&quot;min\&quot;, \&quot;max\&quot;, \&quot;first\&quot;, \&quot;last\&quot;, \&quot;count\&quot;. | [optional] [default to 'avg']
**entityLimit** | **int** | Maximum number of entity series lines to plot concurrently in chart blocks (1-50, default: 10). | [optional] [default to 10]
**min** | **float** | Minimum scale value for gauge blocks (default: 0). | [optional] [default to 0]
**max** | **float** | Maximum scale value for gauge blocks (default: 100). | [optional] [default to 100]
**unit** | **string** | Optional unit suffix for gauge blocks (e.g. \&quot;%\&quot;, \&quot;°C\&quot;, \&quot;MB/s\&quot;, \&quot;req/s\&quot;). | [optional]
**startColor** | **string** | Start gradient hex color for gauge blocks (e.g. \&quot;#3b82f6\&quot;). | [optional]
**midColor** | **string** | Middle gradient hex color for gauge blocks (optional). | [optional]
**endColor** | **string** | End gradient hex color for gauge blocks (e.g. \&quot;#06b6d4\&quot;). | [optional]
**limit** | **int** | Maximum number of rows to return for list table blocks (default: 10). | [optional] [default to 10]
**sort** | **object** | Sort configuration object for list table blocks (e.g. {\&quot;created_at\&quot;: \&quot;desc\&quot;}). | [optional]
**visibleAttributes** | **string[]** | Ordered list of attribute UUIDs (or \&quot;created_at\&quot;, \&quot;updated_at\&quot;) to display as columns in list table blocks. | [optional]
**groupBy** | **string[]** | Attribute slugs or UUIDs to group by, at most 3 (required for aggregate blocks). Lists, references, strings, numbers, booleans and dates can be keys; metrics, markdown, files and images cannot. Empty groups the whole filtered set into one row. | [optional]
**aggregations** | [**\Omnismith\Sdk\Model\CreateDashboardBlockRequestConfigAggregationsInner[]**](CreateDashboardBlockRequestConfigAggregationsInner.md) | Reduces computed per group for aggregate blocks, reported back in this order (1-10 entries; defaults to a single &#x60;count&#x60; when omitted). &#x60;count&#x60; takes no field; &#x60;sum&#x60; and &#x60;avg&#x60; need a number attribute; &#x60;min&#x60; and &#x60;max&#x60; accept number, date and datetime attributes. | [optional]
**filters** | [**\Omnismith\Sdk\Model\CreateDashboardBlockRequestConfigFiltersInner[]**](CreateDashboardBlockRequestConfigFiltersInner.md) | Optional entity filtering conditions applied to block data. | [optional]
**x** | **int** | Horizontal grid column position (0 to 11 on the 12-column grid canvas). | [optional] [default to 0]
**y** | **int** | Vertical grid row position (0 to N, 0-indexed). | [optional] [default to 0]
**cols** | **int** | Block width in columns on the 12-column grid canvas (1 to 12). Guidelines: 12 &#x3D; full-width (chart/list), 6 &#x3D; half-width (chart/gauge, 2 per row), 4 &#x3D; one-third width (stat/gauge, 3 per row), 3 &#x3D; one-fourth width (stat, 4 per row). Sum of cols in a row should equal 12 for edge-to-edge alignment. | [optional]
**rows** | **int** | Block height in grid rows (1 to N). Guidelines: 2 &#x3D; KPI stat / radial gauge, 3-4 &#x3D; time-series chart, 4-5 &#x3D; list table. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
