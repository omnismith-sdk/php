# Omnismith\Sdk\FileAttachmentApi

FileAttachment

All URIs are relative to https://api.omnismith.io/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteFileAttachment()**](FileAttachmentApi.md#deleteFileAttachment) | **DELETE** /file-attachments/{id} | Delete a file attachment |
| [**downloadFileAttachment()**](FileAttachmentApi.md#downloadFileAttachment) | **GET** /file-attachments/{id} | Download a file attachment |
| [**getFileAttachmentMetadata()**](FileAttachmentApi.md#getFileAttachmentMetadata) | **GET** /file-attachments/{id}/metadata | Get file metadata without downloading content |
| [**getFileAttachmentThumbnail()**](FileAttachmentApi.md#getFileAttachmentThumbnail) | **GET** /file-attachments/{id}/thumbnail | Get image thumbnail |
| [**uploadFileAttachment()**](FileAttachmentApi.md#uploadFileAttachment) | **POST** /file-attachments | Upload a file attachment |


## `deleteFileAttachment()`

```php
deleteFileAttachment($id)
```

Delete a file attachment

Permanently deletes a file attachment and its stored content from disk. If the file is referenced by entity attribute values (file or image data type), those references will become stale. Returns 204 on success.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | File attachment UUID to delete

try {
    $apiInstance->deleteFileAttachment($id);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->deleteFileAttachment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| File attachment UUID to delete | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadFileAttachment()`

```php
downloadFileAttachment($id)
```

Download a file attachment

Returns the raw binary file content for a given file attachment ID. The response Content-Type header matches the original uploaded file MIME type. The file must belong to the authenticated user's project.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique UUID identifier of the file attachment to download

try {
    $apiInstance->downloadFileAttachment($id);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->downloadFileAttachment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID identifier of the file attachment to download | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getFileAttachmentMetadata()`

```php
getFileAttachmentMetadata($id): \Omnismith\Sdk\Model\FileAttachmentResponse
```

Get file metadata without downloading content

Returns metadata for a file attachment (original filename, MIME type, file size in bytes, upload timestamp, context) without streaming the binary content. Use this to inspect file properties before deciding whether to download.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique UUID identifier of the file attachment

try {
    $result = $apiInstance->getFileAttachmentMetadata($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->getFileAttachmentMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID identifier of the file attachment | |

### Return type

[**\Omnismith\Sdk\Model\FileAttachmentResponse**](../Model/FileAttachmentResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getFileAttachmentThumbnail()`

```php
getFileAttachmentThumbnail($id, $width, $height)
```

Get image thumbnail

Generates and returns a resized thumbnail for image-type file attachments (JPEG, PNG, WebP, GIF). Optional `width` and `height` query parameters control output dimensions (range 50–1000px, default 200×200). Returns 400 if the file is not an image type. The thumbnail is returned as JPEG binary.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 018b2f1b-8c1a-75b3-8000-7f0000010000; // string | Unique UUID identifier of the image file attachment
$width = 200; // int | Target thumbnail width in pixels (range 50 to 1000, default 200)
$height = 200; // int | Target thumbnail height in pixels (range 50 to 1000, default 200)

try {
    $apiInstance->getFileAttachmentThumbnail($id, $width, $height);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->getFileAttachmentThumbnail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Unique UUID identifier of the image file attachment | |
| **width** | **int**| Target thumbnail width in pixels (range 50 to 1000, default 200) | [optional] [default to 200] |
| **height** | **int**| Target thumbnail height in pixels (range 50 to 1000, default 200) | [optional] [default to 200] |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `image/jpeg`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `uploadFileAttachment()`

```php
uploadFileAttachment($file, $id, $context, $ttlHours): \Omnismith\Sdk\Model\FileAttachmentResponse
```

Upload a file attachment

Uploads a file as a multipart/form-data request. Supported MIME types include images (JPEG, PNG, WebP, GIF, SVG), documents (PDF), spreadsheets (CSV, XLSX), and structured data (JSON, YAML). An optional pre-generated UUIDv7 `id` can be supplied; otherwise the server generates one. The `context` field controls storage lifecycle: \"entity\" files are permanent, \"chat\" files are temporary with configurable `ttl_hours` (default 48h). Returns the file metadata including the assigned ID for use in entity attribute values.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Sdk\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$file = '/path/to/file.txt'; // \SplFileObject
$id = 'id_example'; // string
$context = 'entity'; // string
$ttlHours = 56; // int

try {
    $result = $apiInstance->uploadFileAttachment($file, $id, $context, $ttlHours);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->uploadFileAttachment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **file** | **\SplFileObject****\SplFileObject**|  | |
| **id** | **string**|  | [optional] |
| **context** | **string**|  | [optional] [default to &#39;entity&#39;] |
| **ttlHours** | **int**|  | [optional] |

### Return type

[**\Omnismith\Sdk\Model\FileAttachmentResponse**](../Model/FileAttachmentResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
