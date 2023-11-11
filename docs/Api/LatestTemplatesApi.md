# WheelSizeApiClient\Configurator\LatestTemplatesApi

All URIs are relative to *https://api.wheel-size.com/v2/configurator*

Method | HTTP request | Description
------------- | ------------- | -------------
[**latestTemplatesList**](LatestTemplatesApi.md#latesttemplateslist) | **GET** /latest-templates/ | 

# **latestTemplatesList**
> \WheelSizeApiClient\Configurator\Model\LatestTemplatesReportOutput latestTemplatesList($make, $model, $generation, $year, $body, $ordering, $limit, $offset)



### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\LatestTemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$make = "make_example"; // string | 
$model = "model_example"; // string | 
$generation = "generation_example"; // string | 
$year = 56; // int | 
$body = "body_example"; // string | 
$ordering = "ordering_example"; // string | Comma-separated list without spaces. Supported field names: *`make`*, *`model`*
$limit = 50; // int | 
$offset = 0; // int | 

try {
    $result = $apiInstance->latestTemplatesList($make, $model, $generation, $year, $body, $ordering, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LatestTemplatesApi->latestTemplatesList: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **make** | **string**|  | [optional]
 **model** | **string**|  | [optional]
 **generation** | **string**|  | [optional]
 **year** | **int**|  | [optional]
 **body** | **string**|  | [optional]
 **ordering** | **string**| Comma-separated list without spaces. Supported field names: *&#x60;make&#x60;*, *&#x60;model&#x60;* | [optional]
 **limit** | **int**|  | [optional] [default to 50]
 **offset** | **int**|  | [optional] [default to 0]

### Return type

[**\WheelSizeApiClient\Configurator\Model\LatestTemplatesReportOutput**](../Model/LatestTemplatesReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

