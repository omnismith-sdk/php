# ApproveOAuthAuthorizationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**clientId** | **string** | Client identifier |
**redirectUri** | **string** | Redirection URI to return the authorization code |
**projectId** | **string** | Selected Project UUID that client will be authorized to access |
**codeChallenge** | **string** | PKCE code challenge string (RFC 7636) |
**codeChallengeMethod** | **string** | PKCE challenge transformation method | [optional]
**scopes** | **string[]** | Authorized scope strings | [optional]
**state** | **string** | Opaque client state parameter for CSRF mitigation | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
