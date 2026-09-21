# AggregateEntitiesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**filterGroups** | **\Omnismith\Sdk\Model\EntityFilter[][]** | Narrows the records before grouping. Same grammar as the search endpoint: Filter groups: clauses inside a group are AND-ed, groups are OR-ed. &#x60;[]&#x60; applies no filter, &#x60;[[a, b]]&#x60; is &#x60;a AND b&#x60;, &#x60;[[a], [b, c]]&#x60; is &#x60;a OR (b AND c)&#x60;. | [optional]
**groupBy** | **string[]** | Attribute slugs or UUIDs to group by, at most 3. Lists, references, strings, numbers, booleans and dates can be keys; metrics, markdown, files and images cannot. Empty groups the whole filtered set into one row. | [optional]
**aggregations** | [**\Omnismith\Sdk\Model\AggregateEntitiesRequestAggregationsInner[]**](AggregateEntitiesRequestAggregationsInner.md) | Reduces computed for every group, reported back in this order. &#x60;count&#x60; takes no field; &#x60;sum&#x60; and &#x60;avg&#x60; need a number attribute; &#x60;min&#x60; and &#x60;max&#x60; accept number, date and datetime attributes. |
**limit** | **int** | Maximum number of groups returned (1-100). The response says whether more groups exist. | [optional] [default to 50]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
