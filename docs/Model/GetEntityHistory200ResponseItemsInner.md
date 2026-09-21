# GetEntityHistory200ResponseItemsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**createdAt** | **\DateTime** | Mutation timestamp in ISO 8601 format | [optional]
**attributeId** | **string** | Mutated attribute UUID | [optional]
**oldValue** | **string** | Previous serialized attribute value | [optional]
**value** | **string** | New serialized attribute value | [optional]
**entityId** | **string** | Target entity UUID | [optional]
**authorEmail** | **string** | Actor email who performed the change | [optional]
**actionSlug** | **string** | Slug of the entity action that produced this change, when the write was an action execution rather than a plain update | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
