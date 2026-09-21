# EntityRulePredicate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributeId** | **string** | Attribute UUID the predicate reads |
**operator** | **string** | Comparison operator. &#x60;gt&#x60;/&#x60;gte&#x60;/&#x60;lt&#x60;/&#x60;lte&#x60; apply to number and date attributes, &#x60;contains&#x60;/&#x60;not_contains&#x60; to text, &#x60;in&#x60; to list attributes (value is a list of list item UUIDs), &#x60;eq&#x60;/&#x60;neq&#x60;/&#x60;is_empty&#x60;/&#x60;is_not_empty&#x60; to every non-metric attribute. |
**value** | [**\Omnismith\Sdk\Model\EntityRulePredicateValue**](EntityRulePredicateValue.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
