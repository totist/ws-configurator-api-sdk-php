# WheelSizeApiClient\Configurator\ConfiguratorApi

All URIs are relative to *https://api.wheel-size.com/v2/configurator*

Method | HTTP request | Description
------------- | ------------- | -------------
[**configuratorTemplate**](ConfiguratorApi.md#configuratortemplate) | **GET** /templates/{template}/ | Get detailed info about selected Configurator Template ID
[**configuratorTemplateColors**](ConfiguratorApi.md#configuratortemplatecolors) | **GET** /templates/{template}/colors/ | Get A List of OE colors with names for a specific Configurator Template ID
[**configuratorTemplateRimFit**](ConfiguratorApi.md#configuratortemplaterimfit) | **PUT** /templates/{template}/fit/ | Generate an image of the Configurator Template (vehicle) with the specified rim
[**configuratorTemplates**](ConfiguratorApi.md#configuratortemplates) | **GET** /templates/ | Get A List of Configurator Templates
[**generations**](ConfiguratorApi.md#generations) | **GET** /generations/ | Get A List of Car Generations
[**makes**](ConfiguratorApi.md#makes) | **GET** /makes/ | Get A List of Makes
[**models**](ConfiguratorApi.md#models) | **GET** /models/ | Get A List of Models via Different Filters
[**years**](ConfiguratorApi.md#years) | **GET** /years/ | Get A List of Years

# **configuratorTemplate**
> \WheelSizeApiClient\Configurator\Model\Body configuratorTemplate($template)

Get detailed info about selected Configurator Template ID

Get A List of Configurator Templates

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template = 56; // int | Numeric ID of the Configurator Template (e.g. `448`)

try {
    $result = $apiInstance->configuratorTemplate($template);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->configuratorTemplate: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **template** | **int**| Numeric ID of the Configurator Template (e.g. &#x60;448&#x60;) |

### Return type

[**\WheelSizeApiClient\Configurator\Model\Body**](../Model/Body.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **configuratorTemplateColors**
> \WheelSizeApiClient\Configurator\Model\TemplateColorsReportOutput configuratorTemplateColors($template)

Get A List of OE colors with names for a specific Configurator Template ID

Note: Returns OE info for all *'EVOX'* type Configurator Templates only. For *'manual'* type Configurator Templates 'Not found' message will be shown. Required parameters: *`template`*

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template = 56; // int | Numeric ID of the Configurator Template (e.g. `448`)

try {
    $result = $apiInstance->configuratorTemplateColors($template);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->configuratorTemplateColors: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **template** | **int**| Numeric ID of the Configurator Template (e.g. &#x60;448&#x60;) |

### Return type

[**\WheelSizeApiClient\Configurator\Model\TemplateColorsReportOutput**](../Model/TemplateColorsReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **configuratorTemplateRimFit**
> configuratorTemplateRimFit($template, $url, $file, $color, $brakes, $rba_level)

Generate an image of the Configurator Template (vehicle) with the specified rim

This is a PUT API method. It does the following: + Checks if the provided rim image using *`file`* (raw binary format) or by *`url`* is a real rim image (using neural networks) + Removes the background from the image of the rim if necessary (using neural networks) and prepare image for the next step + Generate an image of the provided Car *`template`* with the specified rim image  Required parameters: *`template`*; One of the following optional parameters: *`file`* or *`url`* also needs to be specified.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template = 56; // int | Numeric ID of the Configurator Template (e.g. `448`)
$url = "url_example"; // string | The rim image URL you want to fit to the specified Configurator Template.   Image requirements:  * the rim should be slightly turned to the side  * min width:250px, min height:250px  Image Example: [link](https://configurator.wheel-size.com/media/public/ENKEI-T6R-Gloss.png) (e.g. `https://configurator.wheel-size.com/media/public/ENKEI-T6R-Gloss.png`)
$file = "/path/to/file"; // \SplFileObject | The rim image you want to fit to the specified Configurator Template.  It can be in multipart HTML form content or raw binary format.
$color = "color_example"; // string | 6 Digit Hex RGB color.  For 'EVOX' type of Configurator Templates use one of OE colors from _**`GET /templates/{template}/colors/`**_For 'manual' type of Configurator Templates it can be any color. (e.g. `1e4b82`)
$brakes = 56; // int | The composite image can be returned without or with a brake disk, black (default) or red caliper color can be specified. Possible values: `0`, `1` and `2`.  Where `0`- no brakes, `1`- black caliper, `2`- red.  If not specified, black caliper color is used. (e.g. `2`)
$rba_level = 56; // int | Rim boundary smoothing level.  As parameter value is increased, the rim boundary blurring width is increased. The value must be odd. If omitted, level `17` is used. (e.g. `17`)

try {
    $apiInstance->configuratorTemplateRimFit($template, $url, $file, $color, $brakes, $rba_level);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->configuratorTemplateRimFit: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **template** | **int**| Numeric ID of the Configurator Template (e.g. &#x60;448&#x60;) |
 **url** | **string**| The rim image URL you want to fit to the specified Configurator Template.   Image requirements:  * the rim should be slightly turned to the side  * min width:250px, min height:250px  Image Example: [link](https://configurator.wheel-size.com/media/public/ENKEI-T6R-Gloss.png) (e.g. &#x60;https://configurator.wheel-size.com/media/public/ENKEI-T6R-Gloss.png&#x60;) | [optional]
 **file** | [**\SplFileObject**](../Model/.md)| The rim image you want to fit to the specified Configurator Template.  It can be in multipart HTML form content or raw binary format. | [optional]
 **color** | **string**| 6 Digit Hex RGB color.  For &#x27;EVOX&#x27; type of Configurator Templates use one of OE colors from _**&#x60;GET /templates/{template}/colors/&#x60;**_For &#x27;manual&#x27; type of Configurator Templates it can be any color. (e.g. &#x60;1e4b82&#x60;) | [optional]
 **brakes** | **int**| The composite image can be returned without or with a brake disk, black (default) or red caliper color can be specified. Possible values: &#x60;0&#x60;, &#x60;1&#x60; and &#x60;2&#x60;.  Where &#x60;0&#x60;- no brakes, &#x60;1&#x60;- black caliper, &#x60;2&#x60;- red.  If not specified, black caliper color is used. (e.g. &#x60;2&#x60;) | [optional]
 **rba_level** | **int**| Rim boundary smoothing level.  As parameter value is increased, the rim boundary blurring width is increased. The value must be odd. If omitted, level &#x60;17&#x60; is used. (e.g. &#x60;17&#x60;) | [optional]

### Return type

void (empty response body)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **configuratorTemplates**
> \WheelSizeApiClient\Configurator\Model\TemplatesReportOutput configuratorTemplates($make, $model, $generation, $year, $body, $ordering, $limit, $offset)

Get A List of Configurator Templates

**NOTE:** A _Configurator Template_ is a vehicle-specific image prepared  for custom rim installation via a URL or file upload.   Returns all Configurator Templates for a specific Car *`make`*_/_*`model`*_/_*`year`* (*`generation`*) parameters.  Required parameters: *`make`*, *`model`*; One of the following optional parameters: *`year`* or *`generation`* also needs to be specified.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$make = "make_example"; // string | Slug of the **`Make`**. A car's **`Make`** is the brand of the vehicle. Use _**`GET /makes/`**_ to get a list of available *`slug`* values. (e.g. `bmw`)
$model = "model_example"; // string | Slug of the **`Model`**. The particular **`Model`** of the brand. Use _**`GET /models/`**_ to get a list of available *`slug`* values. (e.g. `x6`)
$generation = "generation_example"; // string | Slug of the vehicle generation. (e.g. `fd3ae75350`)
$year = "year_example"; // string | Year. Use _**`GET /years/`**_ to get the model years of a specific car make/model  (e.g. `2022`)
$body = "body_example"; // string | Body slug of the vehicle generation. Use _**`GET /generations/`**_ to get list of generations with bodies (e.g. `b7c386cf60`)
$ordering = "ordering_example"; // string | Comma-separated list without spaces. Supported field names: *`make`*, *`model`*
$limit = 50; // int | 
$offset = 0; // int | 

try {
    $result = $apiInstance->configuratorTemplates($make, $model, $generation, $year, $body, $ordering, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->configuratorTemplates: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **make** | **string**| Slug of the **&#x60;Make&#x60;**. A car&#x27;s **&#x60;Make&#x60;** is the brand of the vehicle. Use _**&#x60;GET /makes/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;bmw&#x60;) |
 **model** | **string**| Slug of the **&#x60;Model&#x60;**. The particular **&#x60;Model&#x60;** of the brand. Use _**&#x60;GET /models/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;x6&#x60;) |
 **generation** | **string**| Slug of the vehicle generation. (e.g. &#x60;fd3ae75350&#x60;) | [optional]
 **year** | **string**| Year. Use _**&#x60;GET /years/&#x60;**_ to get the model years of a specific car make/model  (e.g. &#x60;2022&#x60;) | [optional]
 **body** | **string**| Body slug of the vehicle generation. Use _**&#x60;GET /generations/&#x60;**_ to get list of generations with bodies (e.g. &#x60;b7c386cf60&#x60;) | [optional]
 **ordering** | **string**| Comma-separated list without spaces. Supported field names: *&#x60;make&#x60;*, *&#x60;model&#x60;* | [optional]
 **limit** | **int**|  | [optional] [default to 50]
 **offset** | **int**|  | [optional] [default to 0]

### Return type

[**\WheelSizeApiClient\Configurator\Model\TemplatesReportOutput**](../Model/TemplatesReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **generations**
> \WheelSizeApiClient\Configurator\Model\GenerationsReportOutput generations($make, $model, $year, $ordering)

Get A List of Car Generations

Returns all generations for the provided *`make`* and *`model`* parameters Required parameters: *`make`*,  *`model`*; Optional parameter: *`year`*

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$make = "make_example"; // string | Slug of the **`Make`**. A car's **`Make`** is the brand of the vehicle. Use _**`GET /makes/`**_ to get a list of available *`slug`* values. (e.g. `bmw`)
$model = "model_example"; // string | Slug of the **`Model`**. The particular **`Model`** of the brand. Use _**`GET /models/`**_ to get a list of available *`slug`* values. (e.g. `x6`)
$year = "year_example"; // string | Year. Use _**`GET /years/`**_ to get the model years of a specific car make/model  (e.g. `2022`)
$ordering = "ordering_example"; // string | Comma-separated list without spaces. Supported field names: *`start`*

try {
    $result = $apiInstance->generations($make, $model, $year, $ordering);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->generations: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **make** | **string**| Slug of the **&#x60;Make&#x60;**. A car&#x27;s **&#x60;Make&#x60;** is the brand of the vehicle. Use _**&#x60;GET /makes/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;bmw&#x60;) |
 **model** | **string**| Slug of the **&#x60;Model&#x60;**. The particular **&#x60;Model&#x60;** of the brand. Use _**&#x60;GET /models/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;x6&#x60;) |
 **year** | **string**| Year. Use _**&#x60;GET /years/&#x60;**_ to get the model years of a specific car make/model  (e.g. &#x60;2022&#x60;) | [optional]
 **ordering** | **string**| Comma-separated list without spaces. Supported field names: *&#x60;start&#x60;* | [optional]

### Return type

[**\WheelSizeApiClient\Configurator\Model\GenerationsReportOutput**](../Model/GenerationsReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **makes**
> \WheelSizeApiClient\Configurator\Model\MakesReportOutput makes($year, $ordering)

Get A List of Makes

Returns a list of makes based on filters.  Optional parameter: *`year`*

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$year = "year_example"; // string | Year. Use _**`GET /years/`**_ to get the model years of a specific car make/model  (e.g. `2022`)
$ordering = "slug"; // string | Comma-separated list without spaces. Supported field names: *`slug`*

try {
    $result = $apiInstance->makes($year, $ordering);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->makes: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **year** | **string**| Year. Use _**&#x60;GET /years/&#x60;**_ to get the model years of a specific car make/model  (e.g. &#x60;2022&#x60;) | [optional]
 **ordering** | **string**| Comma-separated list without spaces. Supported field names: *&#x60;slug&#x60;* | [optional] [default to slug]

### Return type

[**\WheelSizeApiClient\Configurator\Model\MakesReportOutput**](../Model/MakesReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **models**
> \WheelSizeApiClient\Configurator\Model\ModelsReportOutput models($make, $year, $ordering)

Get A List of Models via Different Filters

Returns relevant information about models based on filters   Required parameter: *`make`*; Optional parameter: *`year`*

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$make = "make_example"; // string | Slug of the **`Make`**. A car's **`Make`** is the brand of the vehicle. Use _**`GET /makes/`**_ to get a list of available *`slug`* values. (e.g. `bmw`)
$year = "year_example"; // string | Year. Use _**`GET /years/`**_ to get the model years of a specific car make/model  (e.g. `2022`)
$ordering = "ordering_example"; // string | Comma-separated list without spaces. Supported field names: *`slug`*

try {
    $result = $apiInstance->models($make, $year, $ordering);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->models: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **make** | **string**| Slug of the **&#x60;Make&#x60;**. A car&#x27;s **&#x60;Make&#x60;** is the brand of the vehicle. Use _**&#x60;GET /makes/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;bmw&#x60;) |
 **year** | **string**| Year. Use _**&#x60;GET /years/&#x60;**_ to get the model years of a specific car make/model  (e.g. &#x60;2022&#x60;) | [optional]
 **ordering** | **string**| Comma-separated list without spaces. Supported field names: *&#x60;slug&#x60;* | [optional]

### Return type

[**\WheelSizeApiClient\Configurator\Model\ModelsReportOutput**](../Model/ModelsReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **years**
> \WheelSizeApiClient\Configurator\Model\YearsReportOutput years($make, $model, $ordering, $limit, $offset)

Get A List of Years

Returns a list of Years based on filters.  Optional key parameters: *`make`*, *`model`*. Basic scenarios of searching by Vehicle Model:   + Year > Make > Model > ... + Make > Model > Year > ... + Make > Model > Generations (Year Ranges) > ...

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure API key authorization: user_key
$config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKey('user_key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WheelSizeApiClient\Configurator\Configuration::getDefaultConfiguration()->setApiKeyPrefix('user_key', 'Bearer');

$apiInstance = new WheelSizeApiClient\Configurator\Api\ConfiguratorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$make = "make_example"; // string | Slug of the **`Make`**. A car's **`Make`** is the brand of the vehicle. Use _**`GET /makes/`**_ to get a list of available *`slug`* values. (e.g. `bmw`)
$model = "model_example"; // string | Slug of the **`Model`**. The particular **`Model`** of the brand. Use _**`GET /models/`**_ to get a list of available *`slug`* values. (e.g. `x6`)
$ordering = "ordering_example"; // string | Comma-separated list without spaces. Supported field names: *`slug`*
$limit = 100; // int | 
$offset = 0; // int | 

try {
    $result = $apiInstance->years($make, $model, $ordering, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfiguratorApi->years: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **make** | **string**| Slug of the **&#x60;Make&#x60;**. A car&#x27;s **&#x60;Make&#x60;** is the brand of the vehicle. Use _**&#x60;GET /makes/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;bmw&#x60;) | [optional]
 **model** | **string**| Slug of the **&#x60;Model&#x60;**. The particular **&#x60;Model&#x60;** of the brand. Use _**&#x60;GET /models/&#x60;**_ to get a list of available *&#x60;slug&#x60;* values. (e.g. &#x60;x6&#x60;) | [optional]
 **ordering** | **string**| Comma-separated list without spaces. Supported field names: *&#x60;slug&#x60;* | [optional]
 **limit** | **int**|  | [optional] [default to 100]
 **offset** | **int**|  | [optional] [default to 0]

### Return type

[**\WheelSizeApiClient\Configurator\Model\YearsReportOutput**](../Model/YearsReportOutput.md)

### Authorization

[user_key](../../README.md#user_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

