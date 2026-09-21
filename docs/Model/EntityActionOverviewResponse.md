# EntityActionOverviewResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Action UUID |
**slug** | **string** | Action slug identifier |
**name** | **string** | Human-readable action name |
**description** | **string** | Action description | [optional]
**isEnabled** | **bool** | Whether the action is active and executable |
**precondition** | [**\Omnismith\Sdk\Model\EntityRulePredicateOverviewResponse[]**](EntityRulePredicateOverviewResponse.md) | Conditions that must hold on the record for the action to be available |
**fields** | [**\Omnismith\Sdk\Model\EntityActionFieldOverviewResponse[]**](EntityActionFieldOverviewResponse.md) | Fields prompted from the operator |
**presets** | [**\Omnismith\Sdk\Model\EntityActionPresetOverviewResponse[]**](EntityActionPresetOverviewResponse.md) | Values written silently upon execution |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
