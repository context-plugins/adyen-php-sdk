
# Time of Day Restriction

## Structure

`TimeOfDayRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?TimeOfDay`](../../doc/models/time-of-day.md) | Optional | - | getValue(): ?TimeOfDay | setValue(?TimeOfDay value): void |

## Example

```php
use AdyenLib\Models\Builders\TimeOfDayRestrictionBuilder;
use AdyenLib\Models\Builders\TimeOfDayBuilder;

$timeOfDayRestriction = TimeOfDayRestrictionBuilder::init(
    'operation0'
)
    ->value(
        TimeOfDayBuilder::init()
            ->endTime('endTime6')
            ->startTime('startTime8')
            ->build()
    )
    ->build();
```

