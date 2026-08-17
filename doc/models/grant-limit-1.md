
# Grant Limit 1

## Structure

`GrantLimit1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The limit amount of the grant account. | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\GrantLimit1Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$grantLimit1 = GrantLimit1Builder::init()
    ->amount(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )->build();
```

