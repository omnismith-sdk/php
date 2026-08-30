# RegisterOAuthClient201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**clientId** | **string** | Generated unique client identifier | [optional]
**clientSecret** | **string** | Client secret for confidential clients (null for public clients) | [optional]
**clientName** | **string** | Registered application name | [optional]
**redirectUris** | **string[]** | Authorized redirection URIs | [optional]
**grantTypes** | **string[]** | Permitted grant types | [optional]
**responseTypes** | **string[]** | Permitted response types | [optional]
**tokenEndpointAuthMethod** | **string** | Authentication method required at token endpoint | [optional]
**clientIdIssuedAt** | **int** | Unix timestamp when client was registered | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
