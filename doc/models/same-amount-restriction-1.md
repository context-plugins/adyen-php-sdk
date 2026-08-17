
# Same Amount Restriction 1

Checks if a user has recently sent the same amount of funds in multiple transfers.

To use this restriction, you must:

- Set the rule `type` to **velocity**.

- Specify a time `interval`.

- Specify a number of `matchingTransactions`.

Supported operation: **equals**.

## Structure

`SameAmountRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | - | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\SameAmountRestriction1Builder;

$sameAmountRestriction1 = SameAmountRestriction1Builder::init(
    'operation6'
)
    ->value(false)
    ->build();
```

