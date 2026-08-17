
# Individual 1

Information about the individual. Required if `type` is **individual**.

## Structure

`Individual1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `birthData` | [`?BirthData1`](../../doc/models/birth-data-1.md) | Optional | The individual's birth information. | getBirthData(): ?BirthData1 | setBirthData(?BirthData1 birthData): void |
| `email` | `?string` | Optional | The email address of the legal entity. | getEmail(): ?string | setEmail(?string email): void |
| `identificationData` | [`?IdentificationData1`](../../doc/models/identification-data-1.md) | Optional | Information about the individual's identification document. | getIdentificationData(): ?IdentificationData1 | setIdentificationData(?IdentificationData1 identificationData): void |
| `name` | [`Name23`](../../doc/models/name-23.md) | Required | The individual's name. | getName(): Name23 | setName(Name23 name): void |
| `nationality` | `?string` | Optional | The individual's nationality. | getNationality(): ?string | setNationality(?string nationality): void |
| `phone` | [`?PhoneNumber2`](../../doc/models/phone-number-2.md) | Optional | The phone number of the legal entity. | getPhone(): ?PhoneNumber2 | setPhone(?PhoneNumber2 phone): void |
| `residentialAddress` | [`Address13`](../../doc/models/address-13.md) | Required | The residential address of the individual. | getResidentialAddress(): Address13 | setResidentialAddress(Address13 residentialAddress): void |
| `support` | [`?Support1`](../../doc/models/support-1.md) | Optional | Support information for the legal entity. Required if you have a platform setup. | getSupport(): ?Support1 | setSupport(?Support1 support): void |
| `taxInformation` | [`?(TaxInformation[])`](../../doc/models/tax-information.md) | Optional | The tax information of the individual. | getTaxInformation(): ?array | setTaxInformation(?array taxInformation): void |
| `webData` | [`?WebData1`](../../doc/models/web-data-1.md) | Optional | The website and app URL of the legal entity. | getWebData(): ?WebData1 | setWebData(?WebData1 webData): void |

## Example

```php
use AdyenLib\Models\Builders\Individual1Builder;
use AdyenLib\Models\Builders\Name23Builder;
use AdyenLib\Models\Builders\Address13Builder;
use AdyenLib\Models\Builders\BirthData1Builder;
use AdyenLib\Models\Builders\IdentificationData1Builder;
use AdyenLib\Models\Type132Enum;
use AdyenLib\Models\Builders\PhoneNumber2Builder;

$individual1 = Individual1Builder::init(
    Name23Builder::init(
        'firstName4',
        'lastName4'
    )
        ->infix('infix4')
        ->build(),
    Address13Builder::init(
        'country6'
    )
        ->city('city2')
        ->postalCode('postalCode4')
        ->stateOrProvince('stateOrProvince0')
        ->street('street2')
        ->street2('street28')
        ->build()
)
    ->birthData(
        BirthData1Builder::init()
            ->dateOfBirth('dateOfBirth8')
            ->build()
    )
    ->email('email8')
    ->identificationData(
        IdentificationData1Builder::init(
            Type132Enum::NATIONALIDNUMBER
        )
            ->cardNumber('cardNumber6')
            ->expiryDate('expiryDate8')
            ->issuerCountry('issuerCountry6')
            ->issuerState('issuerState6')
            ->nationalIdExempt(false)
            ->build()
    )
    ->nationality('nationality6')
    ->phone(
        PhoneNumber2Builder::init(
            'number8'
        )
            ->type('type0')
            ->build()
    )
    ->build();
```

