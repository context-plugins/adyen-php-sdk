
# Vias Phone Number 2

The phone number of the entity.

## Structure

`ViasPhoneNumber2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `phoneCountryCode` | `?string` | Optional | The two-character country code of the phone number.<br><br>> The permitted country codes are defined in ISO-3166-1 alpha-2 (e.g. 'NL'). | getPhoneCountryCode(): ?string | setPhoneCountryCode(?string phoneCountryCode): void |
| `phoneNumber` | `?string` | Optional | The phone number.<br><br>> The inclusion of the phone number country code is not necessary. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `phoneType` | [`?string(PhoneTypeEnum)`](../../doc/models/phone-type-enum.md) | Optional | The type of the phone number.<br><br>> The following values are permitted: `Landline`, `Mobile`, `SIP`, `Fax`. | getPhoneType(): ?string | setPhoneType(?string phoneType): void |

## Example

```php
use AdyenLib\Models\Builders\ViasPhoneNumber2Builder;
use AdyenLib\Models\PhoneTypeEnum;

$viasPhoneNumber2 = ViasPhoneNumber2Builder::init()
    ->phoneCountryCode('phoneCountryCode8')
    ->phoneNumber('phoneNumber0')
    ->phoneType(PhoneTypeEnum::MOBILE)
    ->build();
```

