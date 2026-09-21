# UpdateEntityRuleRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Short name shown in the template editor |
**message** | **string** | Text returned to the client when the rule is violated |
**when** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Full replacement of the activation conditions; empty for an unconditional rule | [optional]
**then** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Full replacement of the constraints |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
