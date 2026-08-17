
# Support 1

Support information for the legal entity. Required if you have a platform setup.

## Structure

`Support1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `email` | `?string` | Optional | The support email address of the legal entity. Required if you have a platform setup. | getEmail(): ?string | setEmail(?string email): void |
| `phone` | [`?PhoneNumber1`](../../doc/models/phone-number-1.md) | Optional | The support phone number of the legal entity. Required if you have a platform setup. | getPhone(): ?PhoneNumber1 | setPhone(?PhoneNumber1 phone): void |

## Example

```php
use AdyenLib\Models\Builders\Support1Builder;
use AdyenLib\Models\Builders\PhoneNumber1Builder;

$support1 = Support1Builder::init()
    ->email('email2')
    ->phone(
        PhoneNumber1Builder::init(
            'number8'
        )
            ->type('type0')
            ->build()
    )
    ->build();
```

