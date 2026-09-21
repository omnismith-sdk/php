# SessionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique UUID identifier of the session | [optional]
**userId** | **string** | UUID of the authenticated user | [optional]
**email** | **string** | Email address of the session owner | [optional]
**ipAddress** | **string** | Client IP address from which the session was established | [optional]
**userAgent** | **string** | User-Agent header string of the client browser/application | [optional]
**createdAt** | **\DateTime** | Timestamp when the session was created | [optional]
**expiresAt** | **\DateTime** | Expiration timestamp after which the session becomes invalid | [optional]
**revokedAt** | **\DateTime** | Timestamp when the session was explicitly revoked | [optional]
**revokedBy** | **string** | User UUID who revoked the session | [optional]
**revokedReason** | **string** | Reason note provided upon session revocation | [optional]
**status** | **string** | Current session status state | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
