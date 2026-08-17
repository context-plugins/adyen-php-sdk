
# Card Order

## Structure

`CardOrder`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `beginDate` | `?DateTime` | Optional | The date when the card order is created. | getBeginDate(): ?\DateTime | setBeginDate(?\DateTime beginDate): void |
| `cardManufacturingProfileId` | `?string` | Optional | The unique identifier of the card manufacturer profile. | getCardManufacturingProfileId(): ?string | setCardManufacturingProfileId(?string cardManufacturingProfileId): void |
| `closedDate` | `?DateTime` | Optional | The date when the card order processing ends. | getClosedDate(): ?\DateTime | setClosedDate(?\DateTime closedDate): void |
| `endDate` | `?DateTime` | Optional | The date when you manually closed the card order.<br><br>Card orders are automatically closed by the end of the day it was created. If you manually closed it beforehand, the closing date is shown as the `endDate`. | getEndDate(): ?\DateTime | setEndDate(?\DateTime endDate): void |
| `id` | `?string` | Optional | The unique identifier of the card order. | getId(): ?string | setId(?string id): void |
| `lockDate` | `?DateTime` | Optional | The date when the card order processing begins. | getLockDate(): ?\DateTime | setLockDate(?\DateTime lockDate): void |
| `serviceCenter` | `?string` | Optional | The service center. | getServiceCenter(): ?string | setServiceCenter(?string serviceCenter): void |
| `status` | [`?string(Status61Enum)`](../../doc/models/status-61-enum.md) | Optional | The status of the card order.<br><br>Possible values: **Open**, **Closed**. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\CardOrderBuilder;
use AdyenLib\Utils\DateTimeHelper;

$cardOrder = CardOrderBuilder::init()
    ->beginDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->cardManufacturingProfileId('cardManufacturingProfileId6')
    ->closedDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->endDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->id('id2')
    ->build();
```

