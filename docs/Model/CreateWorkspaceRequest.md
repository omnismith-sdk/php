# CreateWorkspaceRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Human-readable display name of the workspace (e.g. \&quot;Editorial &amp; Content Calendar\&quot;, \&quot;Guidelines &amp; Strategy\&quot;, \&quot;Media Studio\&quot;) |
**description** | **string** | Detailed description of the workspace purpose and operational domain | [optional]
**layout** | **string** | Multi-pane grid layout arrangement (single, split-v, split-h, quad) | [optional] [default to 'single']
**isDefault** | **bool** | Whether this workspace serves as the default landing view for the project | [optional] [default to false]
**initialTemplateIds** | **string[]** | Optional list of entity template UUIDs or slugs to automatically create and mount as initial view panes in this workspace | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
