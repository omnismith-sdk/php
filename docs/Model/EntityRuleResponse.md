# EntityRuleResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Rule UUID | [optional]
**templateId** | **string** | UUID of the template the rule belongs to | [optional]
**name** | **string** | Short name shown in the template editor | [optional]
**message** | **string** | Text returned to the client when the rule is violated | [optional]
**isEnabled** | **bool** | Disabled rules are stored but not enforced | [optional]
**when** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Conditions that activate the rule; all must hold. Empty means the rule is unconditional. | [optional]
**then** | [**\Omnismith\Sdk\Model\EntityRulePredicate[]**](EntityRulePredicate.md) | Constraints that must hold once the rule is active; at least one. Each failing constraint yields an &#x60;attributes.&lt;slug&gt;&#x60; error. | [optional]
**createdAt** | **\DateTime** |  | [optional]
**updatedAt** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
