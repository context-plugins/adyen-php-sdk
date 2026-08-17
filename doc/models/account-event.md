
# Account Event

## Structure

`AccountEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `event` | [`?string(EventEnum)`](../../doc/models/event-enum.md) | Optional | The event.<br><br>> Permitted values: `InactivateAccount`, `RefundNotPaidOutTransfers`.<br>> For more information, refer to [Verification checks](https://docs.adyen.com/classic-platforms/verification-process). | getEvent(): ?string | setEvent(?string event): void |
| `executionDate` | `?DateTime` | Optional | The date on which the event will take place. | getExecutionDate(): ?\DateTime | setExecutionDate(?\DateTime executionDate): void |
| `reason` | `?string` | Optional | The reason why this event has been created. | getReason(): ?string | setReason(?string reason): void |

## Example

```php
use AdyenLib\Models\Builders\AccountEventBuilder;
use AdyenLib\Models\EventEnum;
use AdyenLib\Utils\DateTimeHelper;

$accountEvent = AccountEventBuilder::init()
    ->event(EventEnum::INACTIVATEACCOUNT)
    ->executionDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->reason('reason0')
    ->build();
```

