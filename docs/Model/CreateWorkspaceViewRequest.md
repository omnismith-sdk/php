# CreateWorkspaceViewRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**templateId** | **string** | Target template ID defining entity schema bound to this view pane |
**name** | **string** | Display label for the view pane tab or header |
**filters** | **object[]** | Dynamic filtering rules applied to entities rendered in this view pane | [optional]
**searchString** | **string** | Initial search query string applied to entities in this view | [optional]
**searchMode** | **string** | Search execution mode (keyword text search or semantic vector similarity search) | [optional] [default to 'keyword']
**sort** | [**\Omnismith\Sdk\Model\CreateWorkspaceViewRequestSort**](CreateWorkspaceViewRequestSort.md) |  | [optional]
**displayMode** | **string** | Presentation layout type for entity records (table or card grid) | [optional] [default to 'table']
**displayedColumns** | **string[]** | List of attribute slugs or UUIDs to display as columns in table mode | [optional]
**paneOrder** | **int** | Display sequence index of this pane within the workspace layout | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
