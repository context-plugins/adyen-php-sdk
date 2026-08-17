
# Shopper Id Payment Method 1

paymentMethod

## Structure

`ShopperIdPaymentMethod1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\ShopperIdPaymentMethod1Builder;

$shopperIdPaymentMethod1 = ShopperIdPaymentMethod1Builder::init()
    ->type('ShopperIdPaymentMethod1')
    ->build();
```

