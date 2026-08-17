
# Meal Voucher FR Info

## Structure

`MealVoucherFRInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conecsId` | `string` | Required | Meal Voucher conecsId. Format: digits only | getConecsId(): string | setConecsId(string conecsId): void |
| `siret` | `string` | Required | Meal Voucher siret. Format: 14 digits.<br><br>**Constraints**: *Minimum Length*: `14`, *Maximum Length*: `14` | getSiret(): string | setSiret(string siret): void |
| `subTypes` | `string[]` | Required | The list of additional payment methods. Allowed values: **mealVoucher_FR_endenred**, **mealVoucher_FR_groupeup**, **mealVoucher_FR_natixis**, **mealVoucher_FR_sodexo**. | getSubTypes(): array | setSubTypes(array subTypes): void |

## Example

```php
use AdyenLib\Models\Builders\MealVoucherFRInfoBuilder;

$mealVoucherFRInfo = MealVoucherFRInfoBuilder::init(
    'conecsId6',
    'siret8',
    [
        'subTypes1'
    ]
)->build();
```

