# InboundEndpointCreatedResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  |
**templateId** | **string** |  |
**name** | **string** |  |
**enabled** | **bool** | A disabled endpoint answers every delivery with 404. |
**url** | **string** | The receive URL to configure in the sender. It is not a secret: the signature authenticates each delivery. |
**signature** | **array<string,mixed>** | How deliveries are authenticated: &#x60;preset&#x60;, plus the effective parameters for &#x60;custom_hmac&#x60; and &#x60;shared_secret_header&#x60;. |
**mapping** | **array<string,mixed>** | How a payload becomes records, with every default filled in (&#x60;on_null&#x60;, &#x60;key.prefix&#x60;, &#x60;timestamp.format&#x60;). |
**deliveryIdSource** | [**\Omnismith\Sdk\Model\InboundDeliveryIdSource**](InboundDeliveryIdSource.md) |  |
**secrets** | [**\Omnismith\Sdk\Model\InboundSecret[]**](InboundSecret.md) | The secrets deliveries are verified with: one, or two while a rotation is under way. Only a hint of each is shown. |
**lastSignatureFailureAt** | **\DateTime** | When a delivery last failed signature verification. A time newer than the last processed delivery usually means the sender uses the wrong secret. |
**createdBy** | **string** | Email of the user who created the endpoint |
**createdAt** | **\DateTime** |  |
**updatedAt** | **\DateTime** |  |
**secret** | [**\Omnismith\Sdk\Model\InboundSecretRevealed**](InboundSecretRevealed.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
