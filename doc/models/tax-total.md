
# Tax Total

## Structure

`TaxTotal`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount`](../../doc/models/amount.md) | Optional | - | getAmount(): ?Amount | setAmount(?Amount amount): void |

## Example

```php
use AdyenLib\Models\Builders\TaxTotalBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$taxTotal = TaxTotalBuilder::init()
    ->amount(
        AmountBuilder::init(
            'currency2',
            110
        )->build()
    )->build();
```

