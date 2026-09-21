# CreateEntityRuleRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Short name shown in the template editor |
**message** | **string** | Text returned to the client when the rule is violated |
**when** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Conditions that activate the rule; all must hold. Omit or send an empty list for an unconditional rule (a plain required field). | [optional]
**then** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Constraints that must hold once the rule is active. &#x60;is_not_empty&#x60; on an attribute is the \&quot;required\&quot; constraint. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
