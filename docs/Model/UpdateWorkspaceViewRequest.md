# UpdateWorkspaceViewRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Updated display label for the view pane tab or header | [optional]
**filters** | **object[]** | Updated dynamic filtering rules applied to entities in this view. Attribute field can be specified by attribute UUID or attribute slug (e.g. [{\&quot;field\&quot;: \&quot;platform\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;&lt;list_item_id_or_slug&gt;\&quot;, \&quot;is_active\&quot;: true}]). | [optional]
**searchString** | **string** | Updated search query string applied to entities in this view | [optional]
**searchMode** | **string** | Updated search execution mode (keyword or semantic) | [optional]
**sort** | [**\Omnismith\Sdk\Model\UpdateWorkspaceViewRequestSort**](UpdateWorkspaceViewRequestSort.md) |  | [optional]
**displayMode** | **string** | Updated presentation layout mode (table or grid) | [optional]
**displayedColumns** | **string[]** | Updated list of attribute UUIDs or slugs to display as columns in table mode (e.g. [\&quot;title\&quot;, \&quot;platform\&quot;, \&quot;status\&quot;, \&quot;scheduled_date\&quot;]) | [optional]
**paneOrder** | **int** | Updated display sequence index within the workspace layout | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
