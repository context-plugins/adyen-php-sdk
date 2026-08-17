
# Meal Voucher FR Response Info 1

**mealVoucher_FR** details

## Structure

`MealVoucherFRResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conecsId` | `?string` | Optional | Meal Voucher conecsId. | getConecsId(): ?string | setConecsId(?string conecsId): void |
| `siret` | `?string` | Optional | Meal Voucher siret. | getSiret(): ?string | setSiret(?string siret): void |
| `subTypes` | `?(string[])` | Optional | The list of additional payment methods. | getSubTypes(): ?array | setSubTypes(?array subTypes): void |

## Example

```php
use AdyenLib\Models\Builders\MealVoucherFRResponseInfo1Builder;

$mealVoucherFRResponseInfo1 = MealVoucherFRResponseInfo1Builder::init()
    ->conecsId('conecsId2')
    ->siret('siret6')
    ->subTypes(
        [
            'subTypes3'
        ]
    )
    ->build();
```

