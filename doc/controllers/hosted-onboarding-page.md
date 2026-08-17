# Hosted Onboarding Page

```php
$hostedOnboardingPageApi = $client->getHostedOnboardingPageApi();
```

## Class Name

`HostedOnboardingPageApi`


# Post-Get Onboarding Url

Returns a link to an Adyen-hosted onboarding page (HOP) that you can send to your account holder. For more information on how to use HOP, refer to [Hosted onboarding](https://docs.adyen.com/classic-platforms/onboard-users/hosted-onboarding-page).

```php
function postGetOnboardingUrl(?GetOnboardingUrlRequest $body = null): GetOnboardingUrlResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetOnboardingUrlRequest`](../../doc/models/get-onboarding-url-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetOnboardingUrlResponse`](../../doc/models/get-onboarding-url-response.md)

## Example Usage

```php
$body = GetOnboardingUrlRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER'
)
    ->returnUrl('https://your.return-url.com/?submerchant=123')
    ->build();

$hostedOnboardingPageApi = $client->getHostedOnboardingPageApi();

try {
    $result = $hostedOnboardingPageApi->postGetOnboardingUrl($body);
    echo 'GetOnboardingUrlResponse:';
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
  "pspReference": "9115677600500127",
  "resultCode": "Success",
  "redirectUrl": "https://hop-test.adyen.com/hop/view/?token=<token>"
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

