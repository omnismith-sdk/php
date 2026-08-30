# SearchEntitiesRequestFiltersInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**field** | **string** | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at) | [optional]
**operator** | **string** | Filter comparison operator: eq (equals), neq (not equals), gt (greater than), lt (less than), like (substring match), not-like (negative match), empty (null/empty), not-empty (has value) | [optional]
**value** | **string** | Comparison value serialized as string (not required for empty and not-empty operators) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
