
# Tax Total 2

Total tax amount from the order.

## Structure

`TaxTotal2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount`](../../doc/models/amount.md) | Optional | - | getAmount(): ?Amount | setAmount(?Amount amount): void |

## Example

```php
use AdyenLib\Models\Builders\TaxTotal2Builder;
use AdyenLib\Models\Builders\AmountBuilder;

$taxTotal2 = TaxTotal2Builder::init()
    ->amount(
        AmountBuilder::init(
            'currency2',
            110
        )->build()
    )->build();
```

