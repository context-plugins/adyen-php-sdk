
# Meal Voucher FR Response Info

## Structure

`MealVoucherFRResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conecsId` | `?string` | Optional | Meal Voucher conecsId. | getConecsId(): ?string | setConecsId(?string conecsId): void |
| `siret` | `?string` | Optional | Meal Voucher siret. | getSiret(): ?string | setSiret(?string siret): void |
| `subTypes` | `?(string[])` | Optional | The list of additional payment methods. | getSubTypes(): ?array | setSubTypes(?array subTypes): void |

## Example

```php
use AdyenLib\Models\Builders\MealVoucherFRResponseInfoBuilder;

$mealVoucherFRResponseInfo = MealVoucherFRResponseInfoBuilder::init()
    ->conecsId('conecsId2')
    ->siret('siret8')
    ->subTypes(
        [
            'subTypes7'
        ]
    )
    ->build();
```

