# PreviewInboundMappingRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**body** | **array<string,mixed>** | A sample payload, as the sender would post it: for example the sample event in the sender&#39;s webhook documentation. | [optional]
**deliveryId** | **string** | A delivery from the endpoint&#39;s log to use as the sample instead: the &#x60;log_id&#x60; the sender was answered with. | [optional]
**mapping** | **array<string,mixed>** | A mapping to try instead of the saved one, in the same shape as the endpoint&#39;s &#x60;mapping&#x60;. It is not saved. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
