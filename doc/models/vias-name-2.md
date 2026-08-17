
# Vias Name 2

The name of the individual.

> Make sure your account holder registers using the name shown on their Photo ID.
> Maximum length: 80 characters
> Cannot contain numbers. /n Cannot be empty.

## Structure

`ViasName2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `gender` | [`?string(GenderEnum)`](../../doc/models/gender-enum.md) | Optional | The gender.<br><br>> The following values are permitted: `MALE`, `FEMALE`, `UNKNOWN`.<br><br>**Constraints**: *Maximum Length*: `1` | getGender(): ?string | setGender(?string gender): void |
| `infix` | `?string` | Optional | The name's infix, if applicable.<br><br>> A maximum length of twenty (20) characters is imposed.<br><br>**Constraints**: *Maximum Length*: `20` | getInfix(): ?string | setInfix(?string infix): void |
| `lastName` | `?string` | Optional | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): ?string | setLastName(?string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\ViasName2Builder;
use AdyenLib\Models\GenderEnum;

$viasName2 = ViasName2Builder::init()
    ->firstName('firstName6')
    ->gender(GenderEnum::UNKNOWN)
    ->infix('infix2')
    ->lastName('lastName2')
    ->build();
```

