
# Fee 2

## Structure

`Fee2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the amount of the grant fee. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\Fee2Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$fee2 = Fee2Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

