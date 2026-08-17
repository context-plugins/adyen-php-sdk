# Taxe Deliveryconsent

```php
$taxeDeliveryconsentApi = $client->getTaxeDeliveryconsentApi();
```

## Class Name

`TaxeDeliveryconsentApi`

## Methods

* [Post-Legal Entities-Id-Check Tax Electronic Delivery Consent](../../doc/controllers/taxe-deliveryconsent.md#post-legal-entities-id-check-tax-electronic-delivery-consent)
* [Post-Legal Entities-Id-Set Tax Electronic Delivery Consent](../../doc/controllers/taxe-deliveryconsent.md#post-legal-entities-id-set-tax-electronic-delivery-consent)


# Post-Legal Entities-Id-Check Tax Electronic Delivery Consent

Returns the consent status for electronic delivery of tax forms.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function postLegalEntitiesIdCheckTaxElectronicDeliveryConsent(
    string $id
): CheckTaxElectronicDeliveryConsentResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity. For sole proprietorships, this is the individual legal entity ID of the owner. For organizations, this is the ID of the organization. |

## Response Type

**200**: OK - the request has succeeded.

[`CheckTaxElectronicDeliveryConsentResponse`](../../doc/models/check-tax-electronic-delivery-consent-response.md)

## Example Usage

```php
$id = 'id0';

$taxEDeliveryConsentApi = $client->getTaxEDeliveryConsentApi();

try {
    $result = $taxEDeliveryConsentApi->postLegalEntitiesIdCheckTaxElectronicDeliveryConsent($id);
    echo 'CheckTaxElectronicDeliveryConsentResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
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


# Post-Legal Entities-Id-Set Tax Electronic Delivery Consent

Set the consent status for electronic delivery of tax forms.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function postLegalEntitiesIdSetTaxElectronicDeliveryConsent(
    string $id,
    ?SetTaxElectronicDeliveryConsentRequest $body = null
): void
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity. For sole proprietorships, this is the individual legal entity ID of the owner. For organizations, this is the ID of the organization. |
| `body` | [`?SetTaxElectronicDeliveryConsentRequest`](../../doc/models/set-tax-electronic-delivery-consent-request.md) | Body, Optional | - |

## Response Type

**200**: No Content - look at the actual response code for the status of the request.

`void`

## Example Usage

```php
$id = 'id0';

$taxEDeliveryConsentApi = $client->getTaxEDeliveryConsentApi();

try {
    $taxEDeliveryConsentApi->postLegalEntitiesIdSetTaxElectronicDeliveryConsent($id);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
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

