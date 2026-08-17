
# Pay to Payment Method

## Structure

`PayToPaymentMethod`

## Inherits From

[`ShopperIdPaymentMethod`](../../doc/models/shopper-id-payment-method.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `shopperReference` | `?string` | Optional | **Constraints**: *Minimum Length*: `0`, *Maximum Length*: `256` | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\PayToPaymentMethodBuilder;

$payToPaymentMethod = PayToPaymentMethodBuilder::init()
    ->type('payTo')
    ->shopperReference('shopperReference8')
    ->build();
```

