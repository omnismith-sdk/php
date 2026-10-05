# ReceiveInboundDelivery200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **string** |  |
**logId** | **string** | The delivery log row |
**entityIds** | **string[]** | Records created or updated |
**reason** | **string** | Why a delivery was skipped | [optional]
**items** | **array<string,mixed>[]** | One result per record: &#x60;index&#x60; in the payload, &#x60;entity_id&#x60;, &#x60;created&#x60;, and the &#x60;error&#x60; body of a record that failed | [optional]
**errors** | **array<string,mixed>** | Record errors of a partial delivery, &#x60;items[i].attributes.&lt;slug&gt;&#x60; &#x3D;&gt; messages | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
