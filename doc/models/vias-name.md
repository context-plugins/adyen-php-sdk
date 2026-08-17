
# Vias Name

## Structure

`ViasName`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `gender` | [`?string(GenderEnum)`](../../doc/models/gender-enum.md) | Optional | The gender.<br><br>> The following values are permitted: `MALE`, `FEMALE`, `UNKNOWN`.<br><br>**Constraints**: *Maximum Length*: `1` | getGender(): ?string | setGender(?string gender): void |
| `infix` | `?string` | Optional | The name's infix, if applicable.<br><br>> A maximum length of twenty (20) characters is imposed.<br><br>**Constraints**: *Maximum Length*: `20` | getInfix(): ?string | setInfix(?string infix): void |
| `lastName` | `?string` | Optional | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): ?string | setLastName(?string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\ViasNameBuilder;
use AdyenLib\Models\GenderEnum;

$viasName = ViasNameBuilder::init()
    ->firstName('firstName2')
    ->gender(GenderEnum::UNKNOWN)
    ->infix('infix6')
    ->lastName('lastName6')
    ->build();
```

