
# Trigger

## Structure

`Trigger`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `schedule` | [`?Schedule21`](../../doc/models/schedule-21.md) | Optional | Contains the details about the schedule that determines when the top up is executed. | getSchedule(): ?Schedule21 | setSchedule(?Schedule21 schedule): void |
| `threshold` | [`Amount17`](../../doc/models/amount-17.md) | Required | The balance threshold that triggers the top-up. If the balance falls below this amount, a top-up is initiated. | getThreshold(): Amount17 | setThreshold(Amount17 threshold): void |

## Example

```php
use AdyenLib\Models\Builders\TriggerBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\Schedule21Builder;
use AdyenLib\Models\ScheduleType1Enum;

$trigger = TriggerBuilder::init(
    Amount17Builder::init(
        'currency8',
        32
    )->build()
)
    ->schedule(
        Schedule21Builder::init(
            ScheduleType1Enum::WEEKDAYS
        )->build()
    )->build();
```

