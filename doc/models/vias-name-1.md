
# Vias Name 1

The name of the person.

## Structure

`ViasName1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `gender` | [`?string(GenderEnum)`](../../doc/models/gender-enum.md) | Optional | The gender.<br><br>> The following values are permitted: `MALE`, `FEMALE`, `UNKNOWN`.<br><br>**Constraints**: *Maximum Length*: `1` | getGender(): ?string | setGender(?string gender): void |
| `infix` | `?string` | Optional | The name's infix, if applicable.<br><br>> A maximum length of twenty (20) characters is imposed.<br><br>**Constraints**: *Maximum Length*: `20` | getInfix(): ?string | setInfix(?string infix): void |
| `lastName` | `?string` | Optional | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): ?string | setLastName(?string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\ViasName1Builder;
use AdyenLib\Models\GenderEnum;

$viasName1 = ViasName1Builder::init()
    ->firstName('firstName8')
    ->gender(GenderEnum::UNKNOWN)
    ->infix('infix0')
    ->lastName('lastName0')
    ->build();
```

