
# Grant Limit

## Structure

`GrantLimit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The amount available on the grant account. | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\GrantLimitBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$grantLimit = GrantLimitBuilder::init()
    ->amount(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )->build();
```

