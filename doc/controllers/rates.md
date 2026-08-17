# Rates

```php
$ratesApi = $client->getRatesApi();
```

## Class Name

`RatesApi`


# Post-Rates-Calculate

Returns the calculated amounts and rates required to convert the currency of a transaction.

:information_source: **Note** This endpoint does not require authentication.

```php
function postRatesCalculate(CalculateRateRequest $body): CalculateRateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CalculateRateRequest`](../../doc/models/calculate-rate-request.md) | Body, Required | - |

## Response Type

**200**: Successful operation

[`CalculateRateResponse`](../../doc/models/calculate-rate-response.md)

## Example Usage

```php
$body = CalculateRateRequestBuilder::init(
    [
        CalculateRateRequestItemBuilder::init(
            ExchangeSide2Enum::BUY,
            Amount19Builder::init(
                'CZK',
                112300
            )->build(),
            'EUR',
            RateType2Enum::SPLITPAYMENT
        )->build(),
        CalculateRateRequestItemBuilder::init(
            ExchangeSide2Enum::SELL,
            Amount19Builder::init(
                'CZK',
                24000
            )->build(),
            'USD',
            RateType2Enum::SPLITREFUND
        )->build()
    ]
)->build();

$ratesApi = $client->getRatesApi();

try {
    $result = $ratesApi->postRatesCalculate($body);
    echo 'CalculateRateResponse:';
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
  "exchangeCalculations": [
    {
      "type": "splitPayment",
      "exchangeSide": "buy",
      "sourceAmount": {
        "value": 112300,
        "currency": "CZK"
      },
      "targetAmount": {
        "value": 4480,
        "currency": "EUR"
      },
      "appliedExchangeRate": 0.039893143366
    },
    {
      "type": "splitRefund",
      "exchangeSide": "sell",
      "sourceAmount": {
        "value": 24000,
        "currency": "CZK"
      },
      "targetAmount": {
        "value": 992,
        "currency": "USD"
      },
      "appliedExchangeRate": 0.0413333333333
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

