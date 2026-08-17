
# Matching Transactions Restriction

## Structure

`MatchingTransactionsRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | The number of transactions. | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\MatchingTransactionsRestrictionBuilder;

$matchingTransactionsRestriction = MatchingTransactionsRestrictionBuilder::init(
    'operation2'
)
    ->value(162)
    ->build();
```

