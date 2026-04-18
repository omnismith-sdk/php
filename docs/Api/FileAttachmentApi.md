# Omnismith\FileAttachmentApi

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

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteFileAttachment($id);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->deleteFileAttachment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->downloadFileAttachment($id);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->downloadFileAttachment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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
getFileAttachmentMetadata($id): \Omnismith\Model\FileAttachmentResponse
```

Get file metadata without downloading content

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

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
| **id** | **string**|  | |

### Return type

[**\Omnismith\Model\FileAttachmentResponse**](../Model/FileAttachmentResponse.md)

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

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$width = 200; // int
$height = 200; // int

try {
    $apiInstance->getFileAttachmentThumbnail($id, $width, $height);
} catch (Exception $e) {
    echo 'Exception when calling FileAttachmentApi->getFileAttachmentThumbnail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **width** | **int**|  | [optional] [default to 200] |
| **height** | **int**|  | [optional] [default to 200] |

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
uploadFileAttachment($file, $id): \Omnismith\Model\FileAttachmentResponse
```

Upload a file attachment

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearerAuth
$config = Omnismith\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Omnismith\Api\FileAttachmentApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$file = '/path/to/file.txt'; // \SplFileObject
$id = 'id_example'; // string

try {
    $result = $apiInstance->uploadFileAttachment($file, $id);
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

### Return type

[**\Omnismith\Model\FileAttachmentResponse**](../Model/FileAttachmentResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
