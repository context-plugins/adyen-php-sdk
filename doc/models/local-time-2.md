
# Local Time 2

The time when the payout funds are settled in your user's transfer instrument.

## Structure

`LocalTime2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hour` | `?int` | Optional | - | getHour(): ?int | setHour(?int hour): void |
| `minute` | `?int` | Optional | - | getMinute(): ?int | setMinute(?int minute): void |
| `nano` | `?int` | Optional | - | getNano(): ?int | setNano(?int nano): void |
| `second` | `?int` | Optional | - | getSecond(): ?int | setSecond(?int second): void |

## Example

```php
use AdyenLib\Models\Builders\LocalTime2Builder;

$localTime2 = LocalTime2Builder::init()
    ->hour(94)
    ->minute(96)
    ->nano(120)
    ->second(158)
    ->build();
```

