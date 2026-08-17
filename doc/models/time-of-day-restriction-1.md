
# Time of Day Restriction 1

A start and end time in a time-only ISO-8601 extended offset format. Supported operations: **equals**, **notEquals**.

## Structure

`TimeOfDayRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?TimeOfDay`](../../doc/models/time-of-day.md) | Optional | - | getValue(): ?TimeOfDay | setValue(?TimeOfDay value): void |

## Example

```php
use AdyenLib\Models\Builders\TimeOfDayRestriction1Builder;
use AdyenLib\Models\Builders\TimeOfDayBuilder;

$timeOfDayRestriction1 = TimeOfDayRestriction1Builder::init(
    'operation8'
)
    ->value(
        TimeOfDayBuilder::init()
            ->endTime('endTime6')
            ->startTime('startTime8')
            ->build()
    )
    ->build();
```

