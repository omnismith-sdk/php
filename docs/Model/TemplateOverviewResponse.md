# TemplateOverviewResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Template UUID |
**slug** | **string** | Unique template slug identifier | [optional]
**name** | **string** | Human-readable template name |
**description** | **string** | Template description | [optional]
**attributes** | [**\Omnismith\Sdk\Model\TemplateAttributeOverviewResponse[]**](TemplateAttributeOverviewResponse.md) | Ordered list of attributes belonging to this template |
**rules** | [**\Omnismith\Sdk\Model\EntityRuleOverviewResponse[]**](EntityRuleOverviewResponse.md) | Business validation rules enforced for this template |
**actions** | [**\Omnismith\Sdk\Model\EntityActionOverviewResponse[]**](EntityActionOverviewResponse.md) | Executable workflow actions and transitions for records of this template |
**inboundEndpoints** | [**\Omnismith\Sdk\Model\InboundEndpointOverviewResponse[]**](InboundEndpointOverviewResponse.md) | Public URLs through which outside systems write records into this template. Empty when the caller cannot view inbound endpoints. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
