
# Timeouts

## Structure

`Timeouts`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fromActiveToSleep` | `?int` | Optional | Indicates the number of seconds of inactivity after which the terminal display goes into sleep mode. | getFromActiveToSleep(): ?int | setFromActiveToSleep(?int fromActiveToSleep): void |

## Example

```php
use AdyenLib\Models\Builders\TimeoutsBuilder;

$timeouts = TimeoutsBuilder::init()
    ->fromActiveToSleep(94)
    ->build();
```

