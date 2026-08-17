
# Card Order Item

## Structure

`CardOrderItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balancePlatform` | `?string` | Optional | The unique identifier of the balance platform. | getBalancePlatform(): ?string | setBalancePlatform(?string balancePlatform): void |
| `card` | [`?CardOrderItemDeliveryStatus3`](../../doc/models/card-order-item-delivery-status-3.md) | Optional | The status of the card delivery.<br><br>Possible values: **created**, **rejected**, **processing**, **produced**, **shipped**, **delivered**, **notApplicable**, **unknown**. | getCard(): ?CardOrderItemDeliveryStatus3 | setCard(?CardOrderItemDeliveryStatus3 card): void |
| `cardOrderItemId` | `?string` | Optional | The unique identifier of the card order item. | getCardOrderItemId(): ?string | setCardOrderItemId(?string cardOrderItemId): void |
| `creationDate` | `?DateTime` | Optional | The date and time when the event was triggered, in ISO 8601 extended format. For example, **2025-03-19T10:15:30+01:00**. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `id` | `?string` | Optional, Read-only | The ID of the resource. | getId(): ?string | setId(?string id): void |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the payment instrument related to the card order item. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |
| `pin` | [`?CardOrderItemDeliveryStatus1`](../../doc/models/card-order-item-delivery-status-1.md) | Optional | Contains information about the status of the PIN delivery. | getPin(): ?CardOrderItemDeliveryStatus1 | setPin(?CardOrderItemDeliveryStatus1 pin): void |
| `shippingMethod` | `?string` | Optional | The shipping method used to deliver the card or the PIN. | getShippingMethod(): ?string | setShippingMethod(?string shippingMethod): void |

## Example

```php
use AdyenLib\Models\Builders\CardOrderItemBuilder;
use AdyenLib\Models\Builders\CardOrderItemDeliveryStatus3Builder;
use AdyenLib\Models\Status71Enum;
use AdyenLib\Utils\DateTimeHelper;

$cardOrderItem = CardOrderItemBuilder::init()
    ->balancePlatform('balancePlatform4')
    ->card(
        CardOrderItemDeliveryStatus3Builder::init()
            ->errorMessage('errorMessage4')
            ->status(Status71Enum::SHIPPED)
            ->trackingNumber('trackingNumber4')
            ->build()
    )
    ->cardOrderItemId('cardOrderItemId8')
    ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

