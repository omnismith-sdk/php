# ApproveOAuthAuthorizationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**clientId** | **string** | Client identifier |
**redirectUri** | **string** | Redirection URI to return the authorization code |
**projectIds** | **string[]** | Every project UUID the client is granted. The first is the project the credential acts on until it selects another, and the set bounds what it can ever reach. There is no wildcard: a grant names its projects explicitly, so it cannot silently widen as the user creates more. |
**codeChallenge** | **string** | PKCE code challenge string (RFC 7636) |
**codeChallengeMethod** | **string** | PKCE challenge transformation method | [optional]
**scopes** | **string[]** | Authorized scope strings | [optional]
**state** | **string** | Opaque client state parameter for CSRF mitigation | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
