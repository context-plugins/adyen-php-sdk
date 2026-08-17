
# Contact 1

The contact details for the shipping location.

## Structure

`Contact1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `email` | `?string` | Optional | The individual's email address. | getEmail(): ?string | setEmail(?string email): void |
| `firstName` | `?string` | Optional | The individual's first name. | getFirstName(): ?string | setFirstName(?string firstName): void |
| `infix` | `?string` | Optional | The infix in the individual's name, if any. | getInfix(): ?string | setInfix(?string infix): void |
| `lastName` | `?string` | Optional | The individual's last name. | getLastName(): ?string | setLastName(?string lastName): void |
| `phoneNumber` | `?string` | Optional | The individual's phone number, specified as 10-14 digits with an optional `+` prefix. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |

## Example

```php
use AdyenLib\Models\Builders\Contact1Builder;

$contact1 = Contact1Builder::init()
    ->email('email6')
    ->firstName('firstName4')
    ->infix('infix4')
    ->lastName('lastName4')
    ->phoneNumber('phoneNumber0')
    ->build();
```

