
# Fee 21

Contains the currency and value of the cashout fee, in [minor units](https://docs.adyen.com/development-resources/currency-codes).

## Structure

`Fee21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the fee amount. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\Fee21Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$fee21 = Fee21Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

