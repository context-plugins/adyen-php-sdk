
# Calculate Rate Response

The response returned when you calculate an amount in a different currency.

## Structure

`CalculateRateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `exchangeCalculations` | [`?(CalculateRateResponseItem[])`](../../doc/models/calculate-rate-response-item.md) | Optional | An array of objects, where each object returns a currency and value for which you performed an exchange calculation. You can use the calculated amounts in your payment requests. | getExchangeCalculations(): ?array | setExchangeCalculations(?array exchangeCalculations): void |

## Example

```php
use AdyenLib\Models\Builders\CalculateRateResponseBuilder;
use AdyenLib\Models\Builders\CalculateRateResponseItemBuilder;
use AdyenLib\Models\Builders\Amount22Builder;
use AdyenLib\Models\Builders\Amount34Builder;

$calculateRateResponse = CalculateRateResponseBuilder::init()
    ->exchangeCalculations(
        [
            CalculateRateResponseItemBuilder::init()
                ->appliedExchangeRate(140.08)
                ->exchangeSide('exchangeSide0')
                ->sourceAmount(
                    Amount22Builder::init(
                        'currency8',
                        232
                    )->build()
                )
                ->targetAmount(
                    Amount34Builder::init(
                        'currency8',
                        168
                    )->build()
                )
                ->type('type2')
                ->build()
        ]
    )
    ->build();
```

