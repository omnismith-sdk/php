# EntityRuleOverviewResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Rule UUID |
**name** | **string** | Short rule name |
**message** | **string** | Error message returned on violation |
**isEnabled** | **bool** | Whether the rule is actively enforced |
**when** | [**\Omnismith\Sdk\Model\EntityRulePredicateOverviewResponse[]**](EntityRulePredicateOverviewResponse.md) | Activating conditions; empty means unconditional |
**then** | [**\Omnismith\Sdk\Model\EntityRulePredicateOverviewResponse[]**](EntityRulePredicateOverviewResponse.md) | Enforced constraints |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
