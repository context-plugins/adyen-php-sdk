
# Calculate Rate Request

The request to calculate an amount in a different currency.

## Structure

`CalculateRateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `exchangeCalculations` | [`CalculateRateRequestItem[]`](../../doc/models/calculate-rate-request-item.md) | Required | An array of objects, where each object defines a currency and value for which you want to perform an exchange calculation.<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `1000` | getExchangeCalculations(): array | setExchangeCalculations(array exchangeCalculations): void |

## Example

```php
use AdyenLib\Models\Builders\CalculateRateRequestBuilder;
use AdyenLib\Models\Builders\CalculateRateRequestItemBuilder;
use AdyenLib\Models\ExchangeSide2Enum;
use AdyenLib\Models\Builders\Amount19Builder;
use AdyenLib\Models\RateType2Enum;

$calculateRateRequest = CalculateRateRequestBuilder::init(
    [
        CalculateRateRequestItemBuilder::init(
            ExchangeSide2Enum::BUY,
            Amount19Builder::init(
                'currency8',
                232
            )->build(),
            'targetCurrency8',
            RateType2Enum::TRANSFER
        )->build()
    ]
)->build();
```

