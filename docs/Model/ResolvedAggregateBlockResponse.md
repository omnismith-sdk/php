# ResolvedAggregateBlockResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**blockId** | **string** | Dashboard block unique identifier | [optional]
**title** | **string** | Block header title | [optional]
**type** | **string** | Block type discriminator | [optional]
**limit** | **int** | Maximum number of groups returned, as configured on the block | [optional]
**truncated** | **bool** | Whether more groups exist beyond &#x60;limit&#x60; | [optional]
**groups** | [**\Omnismith\Sdk\Model\ResolvedAggregateBlockResponseGroupsInner[]**](ResolvedAggregateBlockResponseGroupsInner.md) | One row per group, in the order configured on the block | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
