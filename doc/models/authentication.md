
# Authentication

## Structure

`Authentication`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `email` | `?string` | Optional | The email address where the one-time password (OTP) is sent. | getEmail(): ?string | setEmail(?string email): void |
| `password` | `?string` | Optional | The password used for 3D Secure password-based authentication. The value must be between 1 to 30 characters and must only contain the following supported characters.<br><br>* Characters between **a-z**, **A-Z**, and **0-9**<br><br>* Special characters: **äöüßÄÖÜ+-*/ç%()=?!~#'",;:$&àùòâôûáúó**<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `30` | getPassword(): ?string | setPassword(?string password): void |
| `phone` | [`?Phone11`](../../doc/models/phone-11.md) | Optional | The phone number where the one-time password (OTP) is sent.<br><br>This object must have:<br><br>* A `type` set to **mobile**.<br><br>* A `number` with a valid country code.<br><br>* A `number` with more than 4 digits, excluding the country code.<br><br>> Make sure to verify that the card user owns the phone number. | getPhone(): ?Phone11 | setPhone(?Phone11 phone): void |

## Example

```php
use AdyenLib\Models\Builders\AuthenticationBuilder;
use AdyenLib\Models\Builders\Phone11Builder;
use AdyenLib\Models\Type410Enum;

$authentication = AuthenticationBuilder::init()
    ->email('email8')
    ->password('password2')
    ->phone(
        Phone11Builder::init(
            'number8',
            Type410Enum::LANDLINE
        )->build()
    )->build();
```

