
# Card Order Item Delivery Status 3

The status of the card delivery.

Possible values: **created**, **rejected**, **processing**, **produced**, **shipped**, **delivered**, **notApplicable**, **unknown**.

## Structure

`CardOrderItemDeliveryStatus3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorMessage` | `?string` | Optional | An error message. | getErrorMessage(): ?string | setErrorMessage(?string errorMessage): void |
| `status` | [`?string(Status71Enum)`](../../doc/models/status-71-enum.md) | Optional | The status of the PIN delivery. | getStatus(): ?string | setStatus(?string status): void |
| `trackingNumber` | `?string` | Optional | The tracking number of the PIN delivery. | getTrackingNumber(): ?string | setTrackingNumber(?string trackingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\CardOrderItemDeliveryStatus3Builder;
use AdyenLib\Models\Status71Enum;

$cardOrderItemDeliveryStatus3 = CardOrderItemDeliveryStatus3Builder::init()
    ->errorMessage('errorMessage2')
    ->status(Status71Enum::CREATED)
    ->trackingNumber('trackingNumber2')
    ->build();
```

