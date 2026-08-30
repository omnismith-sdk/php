# MarketplaceBlueprintDetailResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique blueprint UUID | [optional]
**userId** | **string** | UUID of the publisher user | [optional]
**title** | **string** | Blueprint display title | [optional]
**description** | **string** | Detailed markdown description of the blueprint | [optional]
**metadata** | [**\Omnismith\Sdk\Model\MarketplaceBlueprintDetailResponseMetadata**](MarketplaceBlueprintDetailResponseMetadata.md) |  | [optional]
**blueprint** | **object** | JSONB serialized blueprint payload containing templates, attributes, and optional demo entities | [optional]
**isFeatured** | **bool** | Whether the blueprint is featured in the marketplace | [optional]
**createdAt** | **\DateTime** | Publish timestamp | [optional]
**updatedAt** | **\DateTime** | Last update timestamp | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
