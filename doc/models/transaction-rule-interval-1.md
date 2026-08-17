
# Transaction Rule Interval 1

The [time interval](https://docs.adyen.com/issuing/transaction-rules#time-intervals) when the rule conditions apply.

## Structure

`TransactionRuleInterval1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dayOfMonth` | `?int` | Optional | The day of month, used when the `duration.unit` is **months**. If not provided, by default, this is set to **1**, the first day of the month. | getDayOfMonth(): ?int | setDayOfMonth(?int dayOfMonth): void |
| `dayOfWeek` | [`?string(DayOfWeekEnum)`](../../doc/models/day-of-week-enum.md) | Optional | The day of week, used when the `duration.unit` is **weeks**. If not provided, by default, this is set to **monday**.<br><br>Possible values: **sunday**, **monday**, **tuesday**, **wednesday**, **thursday**, **friday**. | getDayOfWeek(): ?string | setDayOfWeek(?string dayOfWeek): void |
| `duration` | [`?Duration1`](../../doc/models/duration-1.md) | Optional | The duration, which you can specify in hours, days, weeks, or months. The maximum duration is 90 days or an equivalent in other units. Required when the `type` is **rolling** or **sliding**. | getDuration(): ?Duration1 | setDuration(?Duration1 duration): void |
| `timeOfDay` | `?string` | Optional | The time of day, in **hh:mm:ss** format, used when the `duration.unit` is **hours**. If not provided, by default, this is set to **00:00:00**. | getTimeOfDay(): ?string | setTimeOfDay(?string timeOfDay): void |
| `timeZone` | `?string` | Optional | The [time zone](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). For example, **Europe/Amsterdam**. By default, this is set to **UTC**. | getTimeZone(): ?string | setTimeZone(?string timeZone): void |
| `type` | [`string(Type131Enum)`](../../doc/models/type-131-enum.md) | Required | The [type of interval](https://docs.adyen.com/issuing/transaction-rules#time-intervals) during which the rule conditions and limits apply, and how often counters are reset.<br><br>Possible values:<br><br>* **perTransaction**: conditions are evaluated and the counters are reset for every transaction.<br>* **daily**: the counters are reset daily at 00:00:00 CET.<br>* **weekly**: the counters are reset every Monday at 00:00:00 CET.<br>* **monthly**: the counters reset every first day of the month at 00:00:00 CET.<br>* **lifetime**: conditions are applied to the lifetime of the payment instrument.<br>* **rolling**: conditions are applied and the counters are reset based on a `duration`. If the reset date and time are not provided, Adyen applies the default reset time similar to fixed intervals. For example, if the duration is every two weeks, the counter resets every third Monday at 00:00:00 CET.<br>* **sliding**: conditions are applied and the counters are reset based on the current time and a `duration` that you specify. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleInterval1Builder;
use AdyenLib\Models\Type131Enum;
use AdyenLib\Models\DayOfWeekEnum;
use AdyenLib\Models\Builders\Duration1Builder;
use AdyenLib\Models\UnitEnum;

$transactionRuleInterval1 = TransactionRuleInterval1Builder::init(
    Type131Enum::DAILY
)
    ->dayOfMonth(96)
    ->dayOfWeek(DayOfWeekEnum::THURSDAY)
    ->duration(
        Duration1Builder::init()
            ->unit(UnitEnum::WEEKS)
            ->value(176)
            ->build()
    )
    ->timeOfDay('timeOfDay0')
    ->timeZone('timeZone2')
    ->build();
```

