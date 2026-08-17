
# Matching Transactions Restriction 1

The number of transactions and the operation.

Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**.

## Structure

`MatchingTransactionsRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | The number of transactions. | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\MatchingTransactionsRestriction1Builder;

$matchingTransactionsRestriction1 = MatchingTransactionsRestriction1Builder::init(
    'operation2'
)
    ->value(116)
    ->build();
```

