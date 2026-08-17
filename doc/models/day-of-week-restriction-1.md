
# Day of Week Restriction 1

List of week days and the operation. Supported operations: **anyMatch**, **noneMatch**.

## Structure

`DayOfWeekRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value1Enum)[])`](../../doc/models/value-1-enum.md) | Optional | List of days of the week.<br><br>Possible values: **monday**, **tuesday**, **wednesday**, **thursday**, **friday**, **saturday**, **sunday**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\DayOfWeekRestriction1Builder;
use AdyenLib\Models\Value1Enum;

$dayOfWeekRestriction1 = DayOfWeekRestriction1Builder::init(
    'operation6'
)
    ->value(
        [
            Value1Enum::TUESDAY
        ]
    )
    ->build();
```

