
# Time of Day

## Structure

`TimeOfDay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endTime` | `?string` | Optional | The end time in a time-only ISO-8601 extended offset format. For example: **08:00:00+02:00**, **22:30:00-03:00**. | getEndTime(): ?string | setEndTime(?string endTime): void |
| `startTime` | `?string` | Optional | The start time in a time-only ISO-8601 extended offset format. For example: **08:00:00+02:00**, **22:30:00-03:00**. | getStartTime(): ?string | setStartTime(?string startTime): void |

## Example

```php
use AdyenLib\Models\Builders\TimeOfDayBuilder;

$timeOfDay = TimeOfDayBuilder::init()
    ->endTime('endTime2')
    ->startTime('startTime0')
    ->build();
```

