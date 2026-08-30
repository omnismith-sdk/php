# UpdateWorkspaceViewRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Updated display label for the view pane tab or header | [optional]
**filters** | **object[]** | Updated dynamic filtering rules applied to entities in this view | [optional]
**searchString** | **string** | Updated search query string applied to entities in this view | [optional]
**searchMode** | **string** | Updated search execution mode (keyword or semantic) | [optional]
**sort** | [**\Omnismith\Sdk\Model\UpdateWorkspaceViewRequestSort**](UpdateWorkspaceViewRequestSort.md) |  | [optional]
**displayMode** | **string** | Updated presentation layout mode (table or grid) | [optional]
**displayedColumns** | **string[]** | Updated list of attribute slugs or UUIDs to display as columns | [optional]
**paneOrder** | **int** | Updated display sequence index within the workspace layout | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
