
# Fee

## Structure

`Fee`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the fee amount. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\FeeBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$fee = FeeBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

