# WorkspaceDetailsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Workspace unique identifier | [optional]
**name** | **string** | Display name of the workspace | [optional]
**description** | **string** | Detailed workspace description | [optional]
**layout** | **string** | Multi-pane layout structure | [optional]
**isDefault** | **bool** | Whether this workspace is designated as the default project view | [optional]
**sortOrder** | **int** | Display ordering index in the workspace navigation switcher | [optional]
**views** | [**\Omnismith\Sdk\Model\WorkspaceViewResponse[]**](WorkspaceViewResponse.md) | Ordered list of view panes attached to this workspace | [optional]
**createdAt** | **\DateTime** | ISO 8601 creation timestamp | [optional]
**updatedAt** | **\DateTime** | ISO 8601 last update timestamp | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
