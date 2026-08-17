# PCI Compliance Questionnaire Page

```php
$pCIComplianceQuestionnairePageApi = $client->getPCIComplianceQuestionnairePageApi();
```

## Class Name

`PCIComplianceQuestionnairePageApi`


# Post-Get Pci Questionnaire Url

Returns a link to a PCI compliance questionnaire that you can send to your account holder.

> You should only use this endpoint if you have a [partner platform setup](https://docs.adyen.com/classic-platforms/platforms-for-partners).

```php
function postGetPciQuestionnaireUrl(?GetPciUrlRequest $body = null): GetPciUrlResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetPciUrlRequest`](../../doc/models/get-pci-url-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetPciUrlResponse`](../../doc/models/get-pci-url-response.md)

## Example Usage

```php
$body = GetPciUrlRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER'
)
    ->returnUrl('https://your.return-url.com/?submerchant=123')
    ->build();

$pCIComplianceQuestionnairePageApi = $client->getPCIComplianceQuestionnairePageApi();

try {
    $result = $pCIComplianceQuestionnairePageApi->postGetPciQuestionnaireUrl($body);
    echo 'GetPciUrlResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "invalidFields": [],
  "pspReference": "8315748692943050",
  "resultCode": "Success",
  "redirectUrl": "https://hop-test.adyen.com/hop/pci/?token=<token>"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |

