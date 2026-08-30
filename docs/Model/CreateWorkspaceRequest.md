# CreateWorkspaceRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Human-readable display name of the workspace |
**description** | **string** | Detailed description of the workspace purpose and workflow | [optional]
**layout** | **string** | Multi-pane grid layout arrangement | [optional] [default to 'split-v']
**isDefault** | **bool** | Whether this workspace serves as the default landing view for the project | [optional] [default to false]
**initialTemplateIds** | **string[]** | Optional list of entity template IDs to automatically create and mount as initial view panes | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
