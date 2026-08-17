
# Calculate Rate Response Item

The response parameters returned when you calculate an amount in a different currency.

## Structure

`CalculateRateResponseItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliedExchangeRate` | `?float` | Optional | The exchange rate to convert the source currency to the target currency. This includes Adyen's markup. | getAppliedExchangeRate(): ?float | setAppliedExchangeRate(?float appliedExchangeRate): void |
| `exchangeSide` | `?string` | Optional | The operation performed on the source amount. Possible values:<br><br>* **buy**<br>* **sell** | getExchangeSide(): ?string | setExchangeSide(?string exchangeSide): void |
| `sourceAmount` | [`?Amount22`](../../doc/models/amount-22.md) | Optional | The currency of the amount you converted (the source amount). | getSourceAmount(): ?Amount22 | setSourceAmount(?Amount22 sourceAmount): void |
| `targetAmount` | [`?Amount34`](../../doc/models/amount-34.md) | Optional | An object specifying the currency and value to which you want to convert the source amount (the target amount). | getTargetAmount(): ?Amount34 | setTargetAmount(?Amount34 targetAmount): void |
| `type` | `?string` | Optional | The type of transaction. Possible values:<br><br>* **splitPayment**: for payments<br>* **splitRefund**: for refunds | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CalculateRateResponseItemBuilder;
use AdyenLib\Models\Builders\Amount22Builder;
use AdyenLib\Models\Builders\Amount34Builder;

$calculateRateResponseItem = CalculateRateResponseItemBuilder::init()
    ->appliedExchangeRate(168.82)
    ->exchangeSide('exchangeSide4')
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
    ->type('type6')
    ->build();
```

