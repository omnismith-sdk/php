# InboundDeliveryDetail

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**receivedAt** | **\DateTime** |  |
**deliveryId** | **string** | The sender&#39;s id for the delivery, when the endpoint names a delivery id source |
**outcome** | **string** | &#x60;processed&#x60;: every record was written. &#x60;partial&#x60;: some records of a multi-record delivery failed. &#x60;skipped&#x60;: the match condition did not hold, or the delivery id was already processed. &#x60;rejected&#x60;: the request was wrong (400, 401, 413, 422). &#x60;failed&#x60;: it could not be written right now (409, 429, 5xx). |
**httpStatus** | **int** | The status the sender was answered with |
**error** | **array<string,mixed>** | The answer&#39;s error body for a non-2xx delivery, &#x60;{errors, items}&#x60; for a partial one, or &#x60;{\&quot;reason\&quot;: ...}&#x60; for a signature failure |
**entityIds** | **string[]** | Records created or updated |
**bodyTruncated** | **bool** | The stored body was cut at 256 KB |
**durationMs** | **int** |  |
**replayOf** | **string** | The delivery this one replayed |
**replayedBy** | **string** | Email of the user who asked for the replay |
**body** | **string** | The raw body as received, at most 256 KB. Null for a delivery that failed signature verification. |
**headers** | **array<string,string>** | The allow-listed request headers: content type, user agent and the delivery id header. Signature headers are never stored. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
