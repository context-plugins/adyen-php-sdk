
# Paginated Get Card Order Response

## Structure

`PaginatedGetCardOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardOrders` | [`?(CardOrder[])`](../../doc/models/card-order.md) | Optional | Contains objects with information about card orders. | getCardOrders(): ?array | setCardOrders(?array cardOrders): void |
| `hasNext` | `bool` | Required | Indicates whether there are more items on the next page. | getHasNext(): bool | setHasNext(bool hasNext): void |
| `hasPrevious` | `bool` | Required | Indicates whether there are more items on the previous page. | getHasPrevious(): bool | setHasPrevious(bool hasPrevious): void |

## Example

```php
use AdyenLib\Models\Builders\PaginatedGetCardOrderResponseBuilder;
use AdyenLib\Models\Builders\CardOrderBuilder;
use AdyenLib\Utils\DateTimeHelper;

$paginatedGetCardOrderResponse = PaginatedGetCardOrderResponseBuilder::init(
    false,
    false
)
    ->cardOrders(
        [
            CardOrderBuilder::init()
                ->beginDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->cardManufacturingProfileId('cardManufacturingProfileId6')
                ->closedDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->endDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id2')
                ->build(),
            CardOrderBuilder::init()
                ->beginDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->cardManufacturingProfileId('cardManufacturingProfileId6')
                ->closedDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->endDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id2')
                ->build(),
            CardOrderBuilder::init()
                ->beginDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->cardManufacturingProfileId('cardManufacturingProfileId6')
                ->closedDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->endDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id2')
                ->build()
        ]
    )
    ->build();
```

