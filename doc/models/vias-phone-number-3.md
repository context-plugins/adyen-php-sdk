
# Vias Phone Number 3

The phone number of the account holder.

> Required if a `fullPhoneNumber` is not provided.

## Structure

`ViasPhoneNumber3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `phoneCountryCode` | `?string` | Optional | The two-character country code of the phone number.<br><br>> The permitted country codes are defined in ISO-3166-1 alpha-2 (e.g. 'NL'). | getPhoneCountryCode(): ?string | setPhoneCountryCode(?string phoneCountryCode): void |
| `phoneNumber` | `?string` | Optional | The phone number.<br><br>> The inclusion of the phone number country code is not necessary. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `phoneType` | [`?string(PhoneTypeEnum)`](../../doc/models/phone-type-enum.md) | Optional | The type of the phone number.<br><br>> The following values are permitted: `Landline`, `Mobile`, `SIP`, `Fax`. | getPhoneType(): ?string | setPhoneType(?string phoneType): void |

## Example

```php
use AdyenLib\Models\Builders\ViasPhoneNumber3Builder;
use AdyenLib\Models\PhoneTypeEnum;

$viasPhoneNumber3 = ViasPhoneNumber3Builder::init()
    ->phoneCountryCode('phoneCountryCode2')
    ->phoneNumber('phoneNumber4')
    ->phoneType(PhoneTypeEnum::MOBILE)
    ->build();
```

