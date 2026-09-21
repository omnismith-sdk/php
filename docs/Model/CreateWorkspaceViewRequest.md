# CreateWorkspaceViewRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**templateId** | **string** | Target template UUID or slug defining entity schema bound to this view pane |
**name** | **string** | Display label for the view pane tab or header (e.g. \&quot;Telegram Channel Hub\&quot;, \&quot;All Pipeline\&quot;) |
**filters** | **object[]** | Dynamic filtering rules applied to entities rendered in this view pane. Attribute field can be specified by attribute UUID or attribute slug (e.g. [{\&quot;field\&quot;: \&quot;platform\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;&lt;list_item_id_or_slug&gt;\&quot;, \&quot;is_active\&quot;: true}]). | [optional]
**searchString** | **string** | Initial search query string applied to entities in this view | [optional]
**searchMode** | **string** | Search execution mode (keyword text search or semantic vector similarity search) | [optional] [default to 'keyword']
**sort** | [**\Omnismith\Sdk\Model\CreateWorkspaceViewRequestSort**](CreateWorkspaceViewRequestSort.md) |  | [optional]
**displayMode** | **string** | Presentation layout type for entity records (table or card grid) | [optional] [default to 'table']
**displayedColumns** | **string[]** | List of attribute UUIDs or slugs to display as columns in table mode (e.g. [\&quot;title\&quot;, \&quot;platform\&quot;, \&quot;status\&quot;, \&quot;scheduled_date\&quot;]) | [optional]
**paneOrder** | **int** | Display sequence index of this pane within the workspace layout | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
