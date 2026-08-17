
# Meal Voucher FR Info 1

Details to provide if `type` is **mealVoucher_FR**.

## Structure

`MealVoucherFRInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conecsId` | `string` | Required | Meal Voucher conecsId. Format: digits only | getConecsId(): string | setConecsId(string conecsId): void |
| `siret` | `string` | Required | Meal Voucher siret. Format: 14 digits.<br><br>**Constraints**: *Minimum Length*: `14`, *Maximum Length*: `14` | getSiret(): string | setSiret(string siret): void |
| `subTypes` | `string[]` | Required | The list of additional payment methods. Allowed values: **mealVoucher_FR_endenred**, **mealVoucher_FR_groupeup**, **mealVoucher_FR_natixis**, **mealVoucher_FR_sodexo**. | getSubTypes(): array | setSubTypes(array subTypes): void |

## Example

```php
use AdyenLib\Models\Builders\MealVoucherFRInfo1Builder;

$mealVoucherFRInfo1 = MealVoucherFRInfo1Builder::init(
    'conecsId2',
    'siret2',
    [
        'subTypes7'
    ]
)->build();
```

