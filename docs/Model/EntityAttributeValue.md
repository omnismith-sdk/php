# EntityAttributeValue

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Canonical attribute definition UUID |
**slug** | **string** | Human-readable attribute slug identifier; null when the attribute has no slug |
**value** | **string** | Raw serialized attribute value (string, numeric string, ISO date, or UUID); empty string when unset |
**customValue** | **string** | Resolved display label (list option label, referenced entity display value, original filename) or the raw value for scalars |
**referenceEntityId** | **string** | Target entity UUID when the attribute kind is reference |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
