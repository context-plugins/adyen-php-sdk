
# Patchable Trigger 2

The condition that triggers the top-up. This can be a recurring schedule or a minimum balance threshold.

## Structure

`PatchableTrigger2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `schedule` | [PatchableSchedule](../../doc/models/patchable-schedule.md)\|null | Optional | This is a container for one-of cases. | getSchedule(): ?PatchableSchedule | setSchedule(?PatchableSchedule schedule): void |
| `threshold` | [`?PatchableAmountDTO1`](../../doc/models/patchable-amount-dto-1.md) | Optional | The balance threshold that triggers the top-up. If the balance falls below this amount, a top-up is initiated. | getThreshold(): ?PatchableAmountDTO1 | setThreshold(?PatchableAmountDTO1 threshold): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableTrigger2Builder;
use AdyenLib\Models\Builders\PatchableScheduleBuilder;
use AdyenLib\Models\ScheduleType1Enum;
use AdyenLib\Models\Builders\PatchableAmountDTO1Builder;

$patchableTrigger2 = PatchableTrigger2Builder::init()
    ->schedule(
        PatchableScheduleBuilder::init()
            ->type(ScheduleType1Enum::MONTHLY)
            ->build()
    )
    ->threshold(
        PatchableAmountDTO1Builder::init()
            ->currency('currency8')
            ->value(32)
            ->build()
    )
    ->build();
```

