# OAuthTokenRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**grantType** | **string** | OAuth 2.0 grant type |
**clientId** | **string** | OAuth client identifier | [optional]
**clientSecret** | **string** | OAuth client secret (for confidential clients) | [optional]
**code** | **string** | Authorization code obtained from /oauth/authorize/approve | [optional]
**redirectUri** | **string** | Original redirection URI matching the authorization request | [optional]
**codeVerifier** | **string** | PKCE code verifier (RFC 7636) | [optional]
**refreshToken** | **string** | Refresh token for grant_type&#x3D;refresh_token | [optional]
**scope** | **string** | Requested scope | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
