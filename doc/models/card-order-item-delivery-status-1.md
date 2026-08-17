
# Card Order Item Delivery Status 1

Contains information about the status of the PIN delivery.

## Structure

`CardOrderItemDeliveryStatus1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorMessage` | `?string` | Optional | An error message. | getErrorMessage(): ?string | setErrorMessage(?string errorMessage): void |
| `status` | [`?string(Status71Enum)`](../../doc/models/status-71-enum.md) | Optional | The status of the PIN delivery. | getStatus(): ?string | setStatus(?string status): void |
| `trackingNumber` | `?string` | Optional | The tracking number of the PIN delivery. | getTrackingNumber(): ?string | setTrackingNumber(?string trackingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\CardOrderItemDeliveryStatus1Builder;
use AdyenLib\Models\Status71Enum;

$cardOrderItemDeliveryStatus1 = CardOrderItemDeliveryStatus1Builder::init()
    ->errorMessage('errorMessage0')
    ->status(Status71Enum::CREATED)
    ->trackingNumber('trackingNumber0')
    ->build();
```

