# SearchEntitiesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**globalSearch** | **string** | Full-text query string searched across all string and text dimension attributes of the template | [optional]
**filterGroups** | **\Omnismith\Sdk\Model\EntityFilter[][]** | Filter groups: clauses inside a group are AND-ed, groups are OR-ed. &#x60;[]&#x60; applies no filter, &#x60;[[a, b]]&#x60; is &#x60;a AND b&#x60;, &#x60;[[a], [b, c]]&#x60; is &#x60;a OR (b AND c)&#x60;. | [optional]
**verbose** | **bool** | When true, each record&#39;s attribute_values is an array of EntityAttributeValue items (attribute id, slug, raw value, resolved custom_value, reference_entity_id). When false (default), attribute_values is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in list_item_ids, reference_entity_ids and file_ids. | [optional] [default to false]
**fields** | **string[]** | Optional list of attribute slugs, attribute UUIDs, or root fields to project (e.g. [\&quot;title\&quot;, \&quot;status\&quot;]). When specified, database queries only hydrate the requested attributes, drastically reducing response payload size and execution latency. If omitted, all attributes defined on the template are returned. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
