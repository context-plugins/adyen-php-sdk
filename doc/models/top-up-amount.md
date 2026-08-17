
# Top Up Amount

## Structure

`TopUpAmount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fixed` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The fixed amount with which you want to top up the balance account. | getFixed(): ?Amount17 | setFixed(?Amount17 fixed): void |
| `target` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The target balance for the balance account that the top-up must achieve. | getTarget(): ?Amount17 | setTarget(?Amount17 target): void |

## Example

```php
use AdyenLib\Models\Builders\TopUpAmountBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$topUpAmount = TopUpAmountBuilder::init()
    ->fixed(
        Amount17Builder::init(
            'currency0',
            164
        )->build()
    )
    ->target(
        Amount17Builder::init(
            'currency2',
            188
        )->build()
    )->build();
```

