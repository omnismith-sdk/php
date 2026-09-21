# ResolvedBlockResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**blockId** | **string** | Dashboard block unique identifier | [optional]
**title** | **string** | Block header title | [optional]
**type** | **string** | Block type discriminator | [optional]
**count** | **int** | Total count of entities matching template and active filter rules | [optional]
**value** | **float** | Current aggregated metric value | [optional]
**min** | **float** | Configured minimum gauge scale bound | [optional]
**max** | **float** | Configured maximum gauge scale bound | [optional]
**percentage** | **float** | Computed progress percentage within [min, max] bounds | [optional]
**bucketWidth** | **string** | Time-bucket aggregation interval applied to telemetry metrics | [optional]
**series** | [**\Omnismith\Sdk\Model\ResolvedChartBlockResponseSeriesInner[]**](ResolvedChartBlockResponseSeriesInner.md) | Time-series data grouped per entity | [optional]
**items** | [**\Omnismith\Sdk\Model\ResolvedListBlockResponseItemsInner[]**](ResolvedListBlockResponseItemsInner.md) | List of matching entity records with hydrated attributes | [optional]
**totalCount** | **int** | Total number of items matching filters | [optional]
**limit** | **int** | Maximum number of groups returned, as configured on the block | [optional]
**truncated** | **bool** | Whether more groups exist beyond &#x60;limit&#x60; | [optional]
**groups** | [**\Omnismith\Sdk\Model\ResolvedAggregateBlockResponseGroupsInner[]**](ResolvedAggregateBlockResponseGroupsInner.md) | One row per group, in the order configured on the block | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
