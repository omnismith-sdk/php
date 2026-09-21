# ValidationErrorResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** |  |
**title** | **string** |  |
**status** | **int** |  |
**errors** | **array<string,string[]>** | Map of field names to array of error messages |
**detail** | **string** |  | [optional]
**violations** | [**\Omnismith\Sdk\Model\ValidationErrorResponseViolationsInner[]**](ValidationErrorResponseViolationsInner.md) | Present when a template&#39;s business rules refused an entity write: one entry per failing constraint, keyed the same way as &#x60;errors&#x60; (&#x60;attributes.&lt;slug&gt;&#x60;) and naming the rule behind it. &#x60;errors&#x60; carries the same messages, so clients that only read &#x60;errors&#x60; keep working. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
