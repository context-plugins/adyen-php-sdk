# Transferroutes

```php
$transferroutesApi = $client->getTransferroutesApi();
```

## Class Name

`TransferroutesApi`


# Post-Transfer Routes-Calculate

Returns available transfer routes based on a combination of transfer `country`, `currency`, `counterparty`, and `priorities`. Use this endpoint to find optimal transfer priorities and associated requirements before you [make a transfer](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers).

```php
function postTransferRoutesCalculate(?TransferRouteRequest $body = null): TransferRouteResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?TransferRouteRequest`](../../doc/models/transfer-route-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`TransferRouteResponse`](../../doc/models/transfer-route-response.md)

## Example Usage

```php
$body = TransferRouteRequestBuilder::init(
    'YOUR_BALANCE_PLATFORM',
    'USD'
)
    ->counterparty(
        Counterparty1Builder::init()
            ->bankAccount(
                BankAccount11Builder::init(
                    IbanAccountIdentificationBuilder::init(
                        'NL91ABNA0417164300'
                    )->build()
                )->build()
            )->build()
    )->build();

$transferRoutesApi = $client->getTransferRoutesApi();

try {
    $result = $transferRoutesApi->postTransferRoutesCalculate($body);
    echo 'TransferRouteResponse:';
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
  "transferRoutes": [
    {
      "country": "NL",
      "currency": "USD",
      "priority": "crossBorder",
      "requirements": [
        {
          "description": "Amount of transfer must be at least 100, and no greater than 99999999999",
          "max": 99999999999,
          "min": 100,
          "type": "amountMinMaxRequirement"
        },
        {
          "description": "Country, street and city is required.",
          "requiredAddressFields": [
            "line1",
            "city",
            "country"
          ],
          "type": "addressRequirement"
        },
        {
          "description": "Bank account identification type must be iban or numberAndBic",
          "bankAccountIdentificationTypes": [
            "iban",
            "numberAndBic"
          ],
          "type": "bankAccountIdentificationTypeRequirement"
        },
        {
          "issuingCountryCode": "NL",
          "paymentInstrumentType": "BankAccount",
          "type": "paymentInstrumentRequirement"
        }
      ]
    },
    {
      "country": "NL",
      "currency": "USD",
      "priority": "wire",
      "requirements": [
        {
          "description": "Amount of transfer must be at least 100, and no greater than 99999999999",
          "max": 99999999999,
          "min": 100,
          "type": "amountMinMaxRequirement"
        },
        {
          "description": "Country, street and city is required.",
          "requiredAddressFields": [
            "line1",
            "city",
            "country"
          ],
          "type": "addressRequirement"
        },
        {
          "description": "Bank account identification type must be iban or numberAndBic",
          "bankAccountIdentificationTypes": [
            "iban",
            "numberAndBic"
          ],
          "type": "bankAccountIdentificationTypeRequirement"
        },
        {
          "issuingCountryCode": "NL",
          "paymentInstrumentType": "BankAccount",
          "type": "paymentInstrumentRequirement"
        }
      ]
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |

