
# Delivery Contact

## Structure

`DeliveryContact`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`StoreLocation`](../../doc/models/store-location.md) | Required | The address of the contact. | getAddress(): StoreLocation | setAddress(StoreLocation address): void |
| `company` | `?string` | Optional | The company name of the contact. | getCompany(): ?string | setCompany(?string company): void |
| `email` | `?string` | Optional | The email address of the contact. | getEmail(): ?string | setEmail(?string email): void |
| `fullPhoneNumber` | `?string` | Optional | The full phone number of the contact provided as a single string. It will be handled as a landline phone.<br>**Examples:** "0031 6 11 22 33 44", "+316/1122-3344", "(0031) 611223344" | getFullPhoneNumber(): ?string | setFullPhoneNumber(?string fullPhoneNumber): void |
| `name` | [`Name`](../../doc/models/name.md) | Required | The name of the contact. | getName(): Name | setName(Name name): void |
| `phoneNumber` | [`?ViasPhoneNumber`](../../doc/models/vias-phone-number.md) | Optional | The phone number of the contact. | getPhoneNumber(): ?ViasPhoneNumber | setPhoneNumber(?ViasPhoneNumber phoneNumber): void |
| `webAddress` | `?string` | Optional | The URL of the contact's website. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
use AdyenLib\Models\Builders\DeliveryContactBuilder;
use AdyenLib\Models\Builders\StoreLocationBuilder;
use AdyenLib\Models\Builders\NameBuilder;
use AdyenLib\Models\Builders\ViasPhoneNumberBuilder;
use AdyenLib\Models\PhoneTypeEnum;

$deliveryContact = DeliveryContactBuilder::init(
    StoreLocationBuilder::init(
        'country0'
    )
        ->city('city6')
        ->line1('line18')
        ->line2('line20')
        ->line3('line38')
        ->postalCode('postalCode8')
        ->build(),
    NameBuilder::init(
        'firstName4',
        'lastName4'
    )->build()
)
    ->company('company4')
    ->email('email0')
    ->fullPhoneNumber('fullPhoneNumber0')
    ->phoneNumber(
        ViasPhoneNumberBuilder::init()
            ->phoneCountryCode('phoneCountryCode8')
            ->phoneNumber('phoneNumber0')
            ->phoneType(PhoneTypeEnum::FAX)
            ->build()
    )
    ->webAddress('webAddress4')
    ->build();
```

