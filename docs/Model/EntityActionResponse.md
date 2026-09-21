# EntityActionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Action UUID | [optional]
**templateId** | **string** | UUID of the template the action belongs to | [optional]
**slug** | **string** | Identifier used in URLs and by agents; unique per template | [optional]
**name** | **string** | Label shown in menus and dialogs | [optional]
**description** | **string** | What the action does, shown in the dialog | [optional]
**icon** | **string** | Material icon name | [optional]
**isEnabled** | **bool** | Disabled actions are stored but neither listed for records nor executable | [optional]
**precondition** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Conditions on the record&#39;s current values that must all hold for the action to be available. Empty means always available. | [optional]
**fields** | [**\Omnismith\Sdk\Model\EntityActionField[]**](EntityActionField.md) | Values the operator is asked for, in dialog order | [optional]
**presets** | [**\Omnismith\Sdk\Model\EntityActionPreset[]**](EntityActionPreset.md) | Values written silently on execution | [optional]
**sortOrder** | **int** | Position among the template&#39;s actions, zero-based | [optional]
**createdAt** | **\DateTime** |  | [optional]
**updatedAt** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
