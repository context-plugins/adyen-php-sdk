
# Fee 22

Contains information about the fee that your user must pay for the disbursement.

## Structure

`Fee22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the amount of the grant fee. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\Fee22Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$fee22 = Fee22Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

