
# UPI Payment Method

## Structure

`UPIPaymentMethod`

## Inherits From

[`ShopperIdPaymentMethod`](../../doc/models/shopper-id-payment-method.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `virtualPaymentAddress` | `?string` | Optional | **Constraints**: *Minimum Length*: `1`, *Maximum Length*: `256` | getVirtualPaymentAddress(): ?string | setVirtualPaymentAddress(?string virtualPaymentAddress): void |

## Example

```php
use AdyenLib\Models\Builders\UPIPaymentMethodBuilder;

$uPIPaymentMethod = UPIPaymentMethodBuilder::init()
    ->type('upi_collect')
    ->virtualPaymentAddress('virtualPaymentAddress6')
    ->build();
```

