
# Contact Details

## Structure

`ContactDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`Address`](../../doc/models/address.md) | Required | The address of the account holder. | getAddress(): Address | setAddress(Address address): void |
| `email` | `string` | Required | The email address of the account holder. | getEmail(): string | setEmail(string email): void |
| `phone` | [`Phone31`](../../doc/models/phone-31.md) | Required | The phone number of the account holder. | getPhone(): Phone31 | setPhone(Phone31 phone): void |
| `webAddress` | `?string` | Optional | The URL of the account holder's website. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
use AdyenLib\Models\Builders\ContactDetailsBuilder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\Phone31Builder;
use AdyenLib\Models\Type410Enum;

$contactDetails = ContactDetailsBuilder::init(
    AddressBuilder::init(
        'city6',
        'country0',
        'houseNumberOrName4',
        'postalCode8',
        'street6'
    )
        ->stateOrProvince('stateOrProvince4')
        ->build(),
    'email6',
    Phone31Builder::init(
        'number8',
        Type410Enum::LANDLINE
    )->build()
)
    ->webAddress('webAddress0')
    ->build();
```

