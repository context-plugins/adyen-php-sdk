
# Fee 4

An object containing the fee currency and value, in [minor units](https://docs.adyen.com/development-resources/currency-codes).

## Structure

`Fee4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the fee amount. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\Fee4Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$fee4 = Fee4Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

