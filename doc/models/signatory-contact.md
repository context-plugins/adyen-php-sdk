
# Signatory Contact

## Structure

`SignatoryContact`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?ViasAddress2`](../../doc/models/vias-address-2.md) | Optional | The address of the person. | getAddress(): ?ViasAddress2 | setAddress(?ViasAddress2 address): void |
| `email` | `?string` | Optional | The e-mail address of the person. | getEmail(): ?string | setEmail(?string email): void |
| `fullPhoneNumber` | `?string` | Optional | The phone number of the person provided as a single string.  It will be handled as a landline phone.<br>Examples: "0031 6 11 22 33 44", "+316/1122-3344", "(0031) 611223344" | getFullPhoneNumber(): ?string | setFullPhoneNumber(?string fullPhoneNumber): void |
| `jobTitle` | `?string` | Optional | Job title of the signatory.<br><br>Example values: **Chief Executive Officer**, **Chief Financial Officer**, **Chief Operating Officer**, **President**, **Vice President**, **Executive President**, **Managing Member**, **Partner**, **Treasurer**, **Director**, or **Other**. | getJobTitle(): ?string | setJobTitle(?string jobTitle): void |
| `name` | [`?ViasName1`](../../doc/models/vias-name-1.md) | Optional | The name of the person. | getName(): ?ViasName1 | setName(?ViasName1 name): void |
| `personalData` | [`?ViasPersonalData1`](../../doc/models/vias-personal-data-1.md) | Optional | Contains information about the person. | getPersonalData(): ?ViasPersonalData1 | setPersonalData(?ViasPersonalData1 personalData): void |
| `phoneNumber` | [`?ViasPhoneNumber1`](../../doc/models/vias-phone-number-1.md) | Optional | The phone number of the person. | getPhoneNumber(): ?ViasPhoneNumber1 | setPhoneNumber(?ViasPhoneNumber1 phoneNumber): void |
| `signatoryCode` | `?string` | Optional | The unique identifier (UUID) of the signatory.<br><br>> **If, during an Account Holder create or update request, this field is left blank (but other fields provided), a new Signatory will be created with a procedurally-generated UUID.**<br><br>> **If, during an Account Holder create request, a UUID is provided, the creation of the Signatory will fail while the creation of the Account Holder will continue.**<br><br>> **If, during an Account Holder update request, a UUID that is not correlated with an existing Signatory is provided, the update of the Signatory will fail.**<br><br>> **If, during an Account Holder update request, a UUID that is correlated with an existing Signatory is provided, the existing Signatory will be updated.** | getSignatoryCode(): ?string | setSignatoryCode(?string signatoryCode): void |
| `signatoryReference` | `?string` | Optional | Your reference for the signatory. | getSignatoryReference(): ?string | setSignatoryReference(?string signatoryReference): void |
| `webAddress` | `?string` | Optional | The URL of the person's website. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
use AdyenLib\Models\Builders\SignatoryContactBuilder;
use AdyenLib\Models\Builders\ViasAddress2Builder;
use AdyenLib\Models\Builders\ViasName1Builder;
use AdyenLib\Models\GenderEnum;

$signatoryContact = SignatoryContactBuilder::init()
    ->address(
        ViasAddress2Builder::init(
            'country0'
        )
            ->city('city6')
            ->houseNumberOrName('houseNumberOrName4')
            ->postalCode('postalCode8')
            ->stateOrProvince('stateOrProvince4')
            ->street('street6')
            ->build()
    )
    ->email('email4')
    ->fullPhoneNumber('fullPhoneNumber6')
    ->jobTitle('jobTitle6')
    ->name(
        ViasName1Builder::init()
            ->firstName('firstName4')
            ->gender(GenderEnum::MALE)
            ->infix('infix4')
            ->lastName('lastName4')
            ->build()
    )
    ->build();
```

