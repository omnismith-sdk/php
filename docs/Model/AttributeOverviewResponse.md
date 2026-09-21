# AttributeOverviewResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Attribute UUID |
**slug** | **string** | Unique slug identifier within the project | [optional]
**name** | **string** | Human-readable attribute name |
**type** | **string** | Semantic data kind: string, number, boolean, datetime, date, file, image, markdown, list, reference, metric |
**description** | **string** | Attribute description | [optional]
**options** | [**\Omnismith\Sdk\Model\ListOptionOverviewResponse[]**](ListOptionOverviewResponse.md) | Selectable choice options for list-type attributes (null for other types) | [optional]
**reference** | [**\Omnismith\Sdk\Model\ReferenceOverviewResponse**](ReferenceOverviewResponse.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
