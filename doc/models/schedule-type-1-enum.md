
# Schedule Type 1 Enum

The type of schedule at which the top up is executed.

* **weekdays**: pull in funds Monday-Friday at 07:00 AM in the local timezone of the balance account.

* **weekly**: pull in funds every Monday at 07:00 AM in the local timezone of the balance account.

* **monthly**: pull in funds every first of the month at 07:00 AM in the local timezone of the balance account.

* **null** (default): continuous monitoring.

## Enumeration

`ScheduleType1Enum`

## Fields

| Name |
|  --- |
| `WEEKDAYS` |
| `WEEKLY` |
| `MONTHLY` |

## Example

```php
use AdyenLib\Models\ScheduleType1Enum;

$scheduleType1 = ScheduleType1Enum::MONTHLY;
```

