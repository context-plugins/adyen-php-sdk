
# Total Amount Restriction 1

The total amount and the operation.

Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**.

## Structure

`TotalAmountRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The amount value and currency. | getValue(): ?Amount17 | setValue(?Amount17 value): void |

## Example

```php
use AdyenLib\Models\Builders\TotalAmountRestriction1Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$totalAmountRestriction1 = TotalAmountRestriction1Builder::init(
    'operation0'
)
    ->value(
        Amount17Builder::init(
            'currency2',
            128
        )->build()
    )->build();
```

