
# Matching Values Restriction 1

Checks if a user has recently made multiple transfers with the specified values.

To use this restriction, you must:

- Set the rule `type` to **velocity**.

- Specify a time `interval`.

- Specify a number of `matchingTransactions`.

Supported operation: **allMatch**.

Supported value inputs:

- **merchantId** and **acquirerId**
- **amount** and **currency**
- **merchantName**.

## Structure

`MatchingValuesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value3Enum)[])`](../../doc/models/value-3-enum.md) | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MatchingValuesRestriction1Builder;
use AdyenLib\Models\Value3Enum;

$matchingValuesRestriction1 = MatchingValuesRestriction1Builder::init(
    'operation0'
)
    ->value(
        [
            Value3Enum::MERCHANTNAME,
            Value3Enum::ACQUIRERID,
            Value3Enum::AMOUNT
        ]
    )
    ->build();
```

