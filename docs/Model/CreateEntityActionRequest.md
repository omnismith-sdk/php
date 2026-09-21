# CreateEntityActionRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slug** | **string** | Identifier used in URLs and by agents; unique per template. Lowercase letters, digits and underscores, starting with a letter. |
**name** | **string** | Label shown in menus and dialogs |
**description** | **string** | What the action does, shown in the dialog | [optional]
**icon** | **string** | Material icon name | [optional]
**precondition** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Conditions on the record&#39;s current values that must all hold for the action to be available. Omit or send an empty list for an action that is always available. | [optional]
**fields** | [**\Omnismith\Sdk\Model\EntityActionField[]**](EntityActionField.md) | Values the operator is asked for, in dialog order. Each attribute may appear once and must not also be a preset. | [optional]
**presets** | [**\Omnismith\Sdk\Model\EntityActionPreset[]**](EntityActionPreset.md) | Values written silently on execution. Each attribute may appear once and must not also be a field. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
