
# Contact Details 1

Contact details of the account holder.

## Structure

`ContactDetails1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`Address`](../../doc/models/address.md) | Required | The address of the account holder. | getAddress(): Address | setAddress(Address address): void |
| `email` | `string` | Required | The email address of the account holder. | getEmail(): string | setEmail(string email): void |
| `phone` | [`Phone31`](../../doc/models/phone-31.md) | Required | The phone number of the account holder. | getPhone(): Phone31 | setPhone(Phone31 phone): void |
| `webAddress` | `?string` | Optional | The URL of the account holder's website. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
use AdyenLib\Models\Builders\ContactDetails1Builder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\Phone31Builder;
use AdyenLib\Models\Type410Enum;

$contactDetails1 = ContactDetails1Builder::init(
    AddressBuilder::init(
        'city6',
        'country0',
        'houseNumberOrName4',
        'postalCode8',
        'street6'
    )
        ->stateOrProvince('stateOrProvince4')
        ->build(),
    'email4',
    Phone31Builder::init(
        'number8',
        Type410Enum::LANDLINE
    )->build()
)
    ->webAddress('webAddress8')
    ->build();
```

