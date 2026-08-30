# GetOAuthAuthorizeInfo200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**clientId** | **string** | OAuth client identifier | [optional]
**clientName** | **string** | Human-readable client application name | [optional]
**redirectUri** | **string** | Validated redirection callback URI | [optional]
**scopes** | **string[]** | List of requested scopes | [optional]
**userEmail** | **string** | Email address of the currently authenticated user | [optional]
**activeProjectId** | **string** | Currently active project ID for the user session | [optional]
**projects** | [**\Omnismith\Sdk\Model\GetOAuthAuthorizeInfo200ResponseProjectsInner[]**](GetOAuthAuthorizeInfo200ResponseProjectsInner.md) | List of projects accessible by the authenticated user | [optional]
**state** | **string** | Echoed client state parameter | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
