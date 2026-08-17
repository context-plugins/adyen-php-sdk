
# Paginated Get Card Order Item Response

## Structure

`PaginatedGetCardOrderItemResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`CardOrderItem[]`](../../doc/models/card-order-item.md) | Required | List of card order items in the card order batch. | getData(): array | setData(array data): void |
| `hasNext` | `bool` | Required | Indicates whether there are more items on the next page. | getHasNext(): bool | setHasNext(bool hasNext): void |
| `hasPrevious` | `bool` | Required | Indicates whether there are more items on the previous page. | getHasPrevious(): bool | setHasPrevious(bool hasPrevious): void |

## Example

```php
use AdyenLib\Models\Builders\PaginatedGetCardOrderItemResponseBuilder;
use AdyenLib\Models\Builders\CardOrderItemBuilder;
use AdyenLib\Models\Builders\CardOrderItemDeliveryStatus3Builder;
use AdyenLib\Models\Status71Enum;
use AdyenLib\Utils\DateTimeHelper;

$paginatedGetCardOrderItemResponse = PaginatedGetCardOrderItemResponseBuilder::init(
    [
        CardOrderItemBuilder::init()
            ->balancePlatform('balancePlatform2')
            ->card(
                CardOrderItemDeliveryStatus3Builder::init()
                    ->errorMessage('errorMessage4')
                    ->status(Status71Enum::SHIPPED)
                    ->trackingNumber('trackingNumber4')
                    ->build()
            )
            ->cardOrderItemId('cardOrderItemId6')
            ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->build()
    ],
    false,
    false
)->build();
```

