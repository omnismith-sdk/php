# GetOAuthServerMetadata200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**issuer** | **string** | Authorization server issuer URL | [optional]
**authorizationEndpoint** | **string** | Interactive user consent URL | [optional]
**tokenEndpoint** | **string** | Token issuance endpoint | [optional]
**registrationEndpoint** | **string** | Dynamic client registration endpoint (RFC 7591) | [optional]
**revocationEndpoint** | **string** | Token revocation endpoint (RFC 7009) | [optional]
**jwksUri** | **string** | JSON Web Key Set URL (RFC 7517) | [optional]
**responseTypesSupported** | **string[]** |  | [optional]
**grantTypesSupported** | **string[]** |  | [optional]
**codeChallengeMethodsSupported** | **string[]** |  | [optional]
**scopesSupported** | **string[]** |  | [optional]
**tokenEndpointAuthMethodsSupported** | **string[]** |  | [optional]
**serviceDocumentation** | **string** | URL of documentation | [optional]
**clientUri** | **string** | URL of the application homepage | [optional]
**logoUri** | **string** | Logo image URL for the authorization server with transparent background | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
