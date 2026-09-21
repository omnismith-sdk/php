# BiListTemplateRowsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**globalSearch** | **string** | Full-text query string searched across all string and text dimension attributes of the template | [optional]
**filterGroups** | **\Omnismith\Sdk\Model\EntityFilter[][]** | Filter groups: clauses inside a group are AND-ed, groups are OR-ed. &#x60;[]&#x60; applies no filter, &#x60;[[a, b]]&#x60; is &#x60;a AND b&#x60;, &#x60;[[a], [b, c]]&#x60; is &#x60;a OR (b AND c)&#x60;. Each clause is &#x60;{field, operator, value}&#x60; — see the &#x60;EntityFilter&#x60; schema for the shape. Unknown fields, operators that do not fit the field, malformed values, and reference paths into a template you cannot view are refused with 400/403. | [optional]
**fields** | **string[]** | Optional list of attribute slugs, UUIDs, or standard fields to project (e.g. [\&quot;price\&quot;, \&quot;sku\&quot;]). Excludes non-requested dynamic attributes from column metadata and row outputs, skipping unnecessary attribute hydration and reducing tabular payload size. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
