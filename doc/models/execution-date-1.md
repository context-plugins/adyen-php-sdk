
# Execution Date 1

Contains information about the date when the transfer will be processed. The execution date must be within 30 days of the current date.

Until the execution date:

- The `status` of the transfer remains as **received**.
- The `reason` of the transfer remains as **pending**.

## Structure

`ExecutionDate1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `date` | `?DateTime` | Optional | The date when the transfer will be processed. This date must be:<br><br>* Within 30 days of the current date.<br>* In the [ISO 8601 format](https://www.iso.org/iso-8601-date-and-time-format.html) **YYYY-MM-DD**. For example: 2025-01-31 | getDate(): ?\DateTime | setDate(?\DateTime date): void |
| `timezone` | `?string` | Optional | The timezone that applies to the execution date. Use a timezone identifier from the [tz database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).<br><br>Example: **America/Los_Angeles**.<br>Default value: **Europe/Amsterdam**. | getTimezone(): ?string | setTimezone(?string timezone): void |

## Example

```php
use AdyenLib\Models\Builders\ExecutionDate1Builder;
use AdyenLib\Utils\DateTimeHelper;

$executionDate1 = ExecutionDate1Builder::init()
    ->date(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->timezone('timezone0')
    ->build();
```

