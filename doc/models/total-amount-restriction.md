
# Total Amount Restriction

## Structure

`TotalAmountRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The amount value and currency. | getValue(): ?Amount17 | setValue(?Amount17 value): void |

## Example

```php
use AdyenLib\Models\Builders\TotalAmountRestrictionBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$totalAmountRestriction = TotalAmountRestrictionBuilder::init(
    'operation4'
)
    ->value(
        Amount17Builder::init(
            'currency2',
            128
        )->build()
    )->build();
```

