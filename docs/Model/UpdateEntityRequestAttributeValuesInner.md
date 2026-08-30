# UpdateEntityRequestAttributeValuesInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attributeId** | **string** | Target attribute UUID (provide either attribute_id or attribute_slug) | [optional]
**attributeSlug** | **string** | Target attribute slug identifier (provide either attribute_id or attribute_slug) | [optional]
**value** | **string** | Serialized attribute value. Formats: String (\&quot;Sample\&quot;), Number (\&quot;123.45\&quot;), Boolean (\&quot;true\&quot;|\&quot;false\&quot;), Date (\&quot;YYYY-MM-DD\&quot;), Datetime (\&quot;YYYY-MM-DD HH:MM:SS\&quot;), List (ListItem UUID), Reference (target Entity UUID) | [optional]
**updatedAt** | **\DateTime** | Observation or mutation timestamp in ISO 8601 or YYYY-MM-DD HH:MM:SS format. Defaults to current UTC time if omitted. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
