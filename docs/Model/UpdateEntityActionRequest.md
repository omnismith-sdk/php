# UpdateEntityActionRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slug** | **string** | Identifier used in URLs and by agents; unique per template. Lowercase letters, digits and underscores, starting with a letter. |
**name** | **string** | Label shown in menus and dialogs |
**description** | **string** | What the action does, shown in the dialog | [optional]
**icon** | **string** | Material icon name | [optional]
**precondition** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Full replacement of the precondition; empty for an action that is always available | [optional]
**fields** | [**\Omnismith\Sdk\Model\EntityActionField[]**](EntityActionField.md) | Full replacement of the fields, in dialog order | [optional]
**presets** | [**\Omnismith\Sdk\Model\EntityActionPreset[]**](EntityActionPreset.md) | Full replacement of the presets | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
