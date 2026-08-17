
# Card Order Item Delivery Status

## Structure

`CardOrderItemDeliveryStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorMessage` | `?string` | Optional | An error message. | getErrorMessage(): ?string | setErrorMessage(?string errorMessage): void |
| `status` | [`?string(Status71Enum)`](../../doc/models/status-71-enum.md) | Optional | The status of the PIN delivery. | getStatus(): ?string | setStatus(?string status): void |
| `trackingNumber` | `?string` | Optional | The tracking number of the PIN delivery. | getTrackingNumber(): ?string | setTrackingNumber(?string trackingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\CardOrderItemDeliveryStatusBuilder;
use AdyenLib\Models\Status71Enum;

$cardOrderItemDeliveryStatus = CardOrderItemDeliveryStatusBuilder::init()
    ->errorMessage('errorMessage2')
    ->status(Status71Enum::SHIPPED)
    ->trackingNumber('trackingNumber2')
    ->build();
```

