# WorkspaceViewResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Workspace view unique identifier | [optional]
**workspaceId** | **string** | Parent workspace unique identifier | [optional]
**templateId** | **string** | Bound entity template unique identifier | [optional]
**name** | **string** | Display name for the view pane tab or header | [optional]
**filters** | **object[]** | Dynamic filter rules applied to entities in this view | [optional]
**searchString** | **string** | Active search query string | [optional]
**searchMode** | **string** | Search execution mode | [optional]
**sort** | [**\Omnismith\Sdk\Model\WorkspaceViewResponseSort**](WorkspaceViewResponseSort.md) |  | [optional]
**displayMode** | **string** | Presentation layout mode | [optional]
**displayedColumns** | **string[]** | List of displayed attribute slugs or UUIDs for table view | [optional]
**paneOrder** | **int** | Display sequence index of this pane within the workspace layout | [optional]
**createdAt** | **\DateTime** | ISO 8601 creation timestamp | [optional]
**updatedAt** | **\DateTime** | ISO 8601 last update timestamp | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
