
# Matching Values Restriction

## Structure

`MatchingValuesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value3Enum)[])`](../../doc/models/value-3-enum.md) | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MatchingValuesRestrictionBuilder;
use AdyenLib\Models\Value3Enum;

$matchingValuesRestriction = MatchingValuesRestrictionBuilder::init(
    'operation6'
)
    ->value(
        [
            Value3Enum::ACQUIRERID,
            Value3Enum::AMOUNT
        ]
    )
    ->build();
```

