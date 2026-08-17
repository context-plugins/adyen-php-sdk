# Managecard PIN

```php
$managecardPINApi = $client->getManagecardPINApi();
```

## Class Name

`ManagecardPINApi`

## Methods

* [Post-Pins-Change](../../doc/controllers/managecard-pin.md#post-pins-change)
* [Post-Pins-Reveal](../../doc/controllers/managecard-pin.md#post-pins-reveal)
* [Get-Public Key](../../doc/controllers/managecard-pin.md#get-public-key)


# Post-Pins-Change

Changes the personal identification number (PIN) of a specified card.

To make this request, your API credential must have the following role:

* Bank Issuing PIN Change Webservice role

```php
function postPinsChange(?PinChangeRequest $body = null): PinChangeResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PinChangeRequest`](../../doc/models/pin-change-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`PinChangeResponse`](../../doc/models/pin-change-response.md)

## Example Usage

```php
$body = PinChangeRequestBuilder::init(
    '75989E8881284D10153ABACF022EEA09F5...',
    '63E5060591EF65F48DD1D4FECD0FECD5',
    'PI6789678967896789',
    '5555341244441115'
)->build();

$manageCardPINApi = $client->getManageCardPINApi();

try {
    $result = $manageCardPINApi->postPinsChange($body);
    echo 'PinChangeResponse:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "status": "completed"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Post-Pins-Reveal

Returns an encrypted PIN block that contains the PIN of a specified card. You can use the decrypted data to reveal the PIN in your user interface.

To make this request, your API credential must have the following role:

* Bank Issuing PIN Reveal Webservice role

```php
function postPinsReveal(?RevealPinRequest $body = null): RevealPinResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?RevealPinRequest`](../../doc/models/reveal-pin-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`RevealPinResponse`](../../doc/models/reveal-pin-response.md)

## Example Usage

```php
$body = RevealPinRequestBuilder::init(
    '75989E8881284D10153ABACF022EEA09F5...',
    'PI3227C223222B5BPCMFXD2XG'
)->build();

$manageCardPINApi = $client->getManageCardPINApi();

try {
    $result = $manageCardPINApi->postPinsReveal($body);
    echo 'RevealPinResponse:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "encryptedPinBlock": "63E5060591EF65F48DD1D4FECD0FECD5",
  "token": "5555341244441115"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Get-Public Key

Get an [RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem)) public key to encrypt or decrypt card data.

You need the RSA public key to generate the `encryptedKey` required to:

- [Change a PIN](https://docs.adyen.com/api-explorer/balanceplatform/2/post/pins/change).
- [Reveal a PIN](https://docs.adyen.com/api-explorer/balanceplatform/2/post/pins/reveal).
- [Reveal a PAN](https://docs.adyen.com/api-explorer/balanceplatform/2/post/paymentInstruments/reveal).

```php
function getPublicKey(?string $purpose = null, ?string $format = null): PublicKeyResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purpose` | `?string` | Query, Optional | The purpose of the public key.<br><br>Possible values: **pinChange**, **pinReveal**, **panReveal**.<br><br>Default value: **pinReveal**. |
| `format` | `?string` | Query, Optional | The encoding format of public key.<br><br>Possible values: **jwk**, **pem**.<br><br>Default value: **pem**. |

## Response Type

**200**: OK - the request has succeeded.

[`PublicKeyResponse`](../../doc/models/public-key-response.md)

## Example Usage

```php
$manageCardPINApi = $client->getManageCardPINApi();

try {
    $result = $manageCardPINApi->getPublicKey();
    echo 'PublicKeyResponse:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "publicKey": "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMII...",
  "publicKeyExpiryDate": "2023-12-12"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |

