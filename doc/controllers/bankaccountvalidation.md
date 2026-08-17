# Bankaccountvalidation

```php
$bankaccountvalidationApi = $client->getBankaccountvalidationApi();
```

## Class Name

`BankaccountvalidationApi`


# Post-Validate Bank Account Identification

Validates bank account identification details. You can use this endpoint to validate bank account details before you [make a transfer](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers) or [create a transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments).

```php
function postValidateBankAccountIdentification(?BankAccountIdentificationValidationRequest $body = null): void
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?BankAccountIdentificationValidationRequest`](../../doc/models/bank-account-identification-validation-request.md) | Body, Optional | - |

## Response Type

**200**: No Content - look at the actual response code for the status of the request.

`void`

## Example Usage

```php
$body = BankAccountIdentificationValidationRequestBuilder::init(
    IbanAccountIdentificationBuilder::init(
        '1001001234'
    )->build()
)->build();

$bankAccountValidationApi = $client->getBankAccountValidationApi();

try {
    $bankAccountValidationApi->postValidateBankAccountIdentification($body);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |

