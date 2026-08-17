
# Shopper Id Payment Method

## Structure

`ShopperIdPaymentMethod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\UPIPaymentMethodBuilder;

$shopperIdPaymentMethod = UPIPaymentMethodBuilder::init()
    ->type('upi_collect')
    ->virtualPaymentAddress('virtualPaymentAddress4')
    ->build();
```

