
# Calculate Rate Request Item

The request parameters required to calculate an amount in a different currency.

## Structure

`CalculateRateRequestItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `exchangeSide` | [`string(ExchangeSide2Enum)`](../../doc/models/exchange-side-2-enum.md) | Required | The operation performed on the source amount. Possible values:<br><br>* **buy**<br>* **sell** | getExchangeSide(): string | setExchangeSide(string exchangeSide): void |
| `sourceAmount` | [`Amount19`](../../doc/models/amount-19.md) | Required | An object specifying the currency and value for which you want to perform an exchange calculation. | getSourceAmount(): Amount19 | setSourceAmount(Amount19 sourceAmount): void |
| `targetCurrency` | `string` | Required | The currency to which you want to convert the source amount. | getTargetCurrency(): string | setTargetCurrency(string targetCurrency): void |
| `type` | [`string(RateType2Enum)`](../../doc/models/rate-type-2-enum.md) | Required | The type of transaction. Possible values:<br><br>* **splitPayment**: for payments<br>* **splitRefund**: for refunds | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\CalculateRateRequestItemBuilder;
use AdyenLib\Models\ExchangeSide2Enum;
use AdyenLib\Models\Builders\Amount19Builder;
use AdyenLib\Models\RateType2Enum;

$calculateRateRequestItem = CalculateRateRequestItemBuilder::init(
    ExchangeSide2Enum::BUY,
    Amount19Builder::init(
        'currency8',
        232
    )->build(),
    'targetCurrency8',
    RateType2Enum::TRANSFER
)->build();
```

