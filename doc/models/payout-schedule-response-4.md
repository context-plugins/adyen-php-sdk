
# Payout Schedule Response 4

The account's payout schedule.

## Structure

`PayoutScheduleResponse4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `nextScheduledPayout` | `?DateTime` | Optional | The date of the next scheduled payout. | getNextScheduledPayout(): ?\DateTime | setNextScheduledPayout(?\DateTime nextScheduledPayout): void |
| `schedule` | [`?string(ScheduleEnum)`](../../doc/models/schedule-enum.md) | Optional | The payout schedule for the account.<br><br>Possible values: `DEFAULT`, `DAILY`, `DAILY_US`, `DAILY_EU`, `DAILY_AU`, `DAILY_SG`, `WEEKLY`, `WEEKLY_ON_TUE_FRI_MIDNIGHT`, `BIWEEKLY_ON_1ST_AND_15TH_AT_MIDNIGHT`, `MONTHLY`, `HOLD`.<br><br>> `HOLD` prevents scheduled payouts, but you can still initiate payouts manually. | getSchedule(): ?string | setSchedule(?string schedule): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutScheduleResponse4Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\ScheduleEnum;

$payoutScheduleResponse4 = PayoutScheduleResponse4Builder::init()
    ->nextScheduledPayout(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->schedule(ScheduleEnum::DAILY_AU)
    ->build();
```

