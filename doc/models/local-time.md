
# Local Time

## Structure

`LocalTime`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hour` | `?int` | Optional | - | getHour(): ?int | setHour(?int hour): void |
| `minute` | `?int` | Optional | - | getMinute(): ?int | setMinute(?int minute): void |
| `nano` | `?int` | Optional | - | getNano(): ?int | setNano(?int nano): void |
| `second` | `?int` | Optional | - | getSecond(): ?int | setSecond(?int second): void |

## Example

```php
use AdyenLib\Models\Builders\LocalTimeBuilder;

$localTime = LocalTimeBuilder::init()
    ->hour(74)
    ->minute(76)
    ->nano(100)
    ->second(138)
    ->build();
```

