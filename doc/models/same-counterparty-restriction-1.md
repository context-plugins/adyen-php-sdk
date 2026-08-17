
# Same Counterparty Restriction 1

Checks if a user has recently made multiple transfers to the same counterparty.

To use this restriction, you must:

- Set the rule `type` to **velocity**.

- Specify a time `interval`.

- Specify a number of `matchingTransactions`.

Supported operations: **equals**.

## Structure

`SameCounterpartyRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | - | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\SameCounterpartyRestriction1Builder;

$sameCounterpartyRestriction1 = SameCounterpartyRestriction1Builder::init(
    'operation6'
)
    ->value(false)
    ->build();
```

