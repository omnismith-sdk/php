# EntityFilter

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**field** | **string** | Attribute slug or UUID, a standard field (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;), or a one-hop path through a reference attribute: &#x60;&lt;reference&gt;.&lt;attribute of its target template&gt;&#x60; (e.g. &#x60;customer.tier&#x60;). |
**operator** | **string** | eq, neq, gt, lt, like (case-insensitive substring), not-like, empty, not-empty, in, not-in, between |
**value** | [**\Omnismith\Sdk\Model\EntityFilterValue**](EntityFilterValue.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
