
# Day of Week Restriction

## Structure

`DayOfWeekRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value1Enum)[])`](../../doc/models/value-1-enum.md) | Optional | List of days of the week.<br><br>Possible values: **monday**, **tuesday**, **wednesday**, **thursday**, **friday**, **saturday**, **sunday**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\DayOfWeekRestrictionBuilder;
use AdyenLib\Models\Value1Enum;

$dayOfWeekRestriction = DayOfWeekRestrictionBuilder::init(
    'operation2'
)
    ->value(
        [
            Value1Enum::THURSDAY,
            Value1Enum::TUESDAY
        ]
    )
    ->build();
```

