# Cash Out

```php
$cashOutApi = $client->getCashOutApi();
```

## Class Name

`CashOutApi`


# Post-Cashouts

Initiates a [cashout](https://docs.adyen.com/platforms/cash-out-instantly) request.

:information_source: **Note** This endpoint does not require authentication.

```php
function postCashouts(CashOutInfo $body): CashOut
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CashOutInfo`](../../doc/models/cash-out-info.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`CashOut`](../../doc/models/cash-out.md)

## Example Usage

```php
$body = CashOutInfoBuilder::init(
    Amount17Builder::init(
        'EUR',
        50000
    )->build(),
    'BA00000000000000000000001'
)
    ->counterparty(
        CashOutInfoCounterparty1Builder::init()
            ->transferInstrumentId('SE00000000000000000000001')
            ->build()
    )
    ->description('Cashout to bank account')
    ->fee(
        Fee21Builder::init(
            Amount17Builder::init(
                'EUR',
                500
            )->build()
        )->build()
    )
    ->referenceForBeneficiary('CASHOUT-REF-001')
    ->build();

$cashOutApi = $client->getCashOutApi();

try {
    $result = $cashOutApi->postCashouts($body);
    echo 'CashOut:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "CO00000000000000000000001",
  "instructingBalanceAccountId": "BA00000000000000000000001",
  "amount": {
    "currency": "EUR",
    "value": 50000
  },
  "counterparty": {
    "transferInstrumentId": "SE00000000000000000000001"
  },
  "description": "Cashout to bank account",
  "referenceForBeneficiary": "CASHOUT-REF-001",
  "fee": {
    "amount": {
      "currency": "EUR",
      "value": 500
    }
  },
  "transfers": [
    {
      "id": "400F6060JMB1I0AB",
      "type": "cashoutRepayment",
      "amount": {
        "currency": "EUR",
        "value": 50500
      }
    },
    {
      "id": "400F6060JMB1I0AA",
      "type": "cashoutFee",
      "amount": {
        "currency": "EUR",
        "value": 500
      }
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request is malformed or is not in the expected format. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - The API credential used in the request is invalid. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - The API credential does not have the right permissions. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - The requested resource was not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 429 | Too Many Requests - Request rate limit exceeded. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Service Error - An unrecoverable error occurred while trying to perform the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

