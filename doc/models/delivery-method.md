
# Delivery Method

## Structure

`DeliveryMethod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount24`](../../doc/models/amount-24.md) | Optional | The cost of this delivery method. | getAmount(): ?Amount24 | setAmount(?Amount24 amount): void |
| `description` | `?string` | Optional | The name of the delivery method as shown to the shopper. | getDescription(): ?string | setDescription(?string description): void |
| `reference` | `?string` | Optional | The reference of the delivery method. | getReference(): ?string | setReference(?string reference): void |
| `selected` | `?bool` | Optional | If you display the PayPal lightbox with delivery methods, set to **true** for the delivery method that is selected. Only one delivery method can be selected at a time. | getSelected(): ?bool | setSelected(?bool selected): void |
| `type` | [`?string(Type21Enum)`](../../doc/models/type-21-enum.md) | Optional | The type of the delivery method. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\DeliveryMethodBuilder;
use AdyenLib\Models\Builders\Amount24Builder;
use AdyenLib\Models\Type21Enum;

$deliveryMethod = DeliveryMethodBuilder::init()
    ->amount(
        Amount24Builder::init(
            'currency2',
            110
        )->build()
    )
    ->description('description8')
    ->reference('reference6')
    ->selected(false)
    ->type(Type21Enum::SHIPPING)
    ->build();
```

