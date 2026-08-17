
# Phone Number

## Structure

`PhoneNumber`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `string` | Required | The full phone number, including the country code. For example, **+3112345678**. | getNumber(): string | setNumber(string number): void |
| `phoneCountryCode` | `?string` | Optional, Read-only | The two-letter [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code prefix of the phone number. For example, **US** or **NL**.<br><br>The value of the `phoneCountryCode` is determined by the country code digit(s) of `phone.number` | getPhoneCountryCode(): ?string | setPhoneCountryCode(?string phoneCountryCode): void |
| `type` | `?string` | Optional | The type of phone number.<br>Possible values: **mobile**, **landline**, **sip**, **fax.** | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\PhoneNumberBuilder;

$phoneNumber = PhoneNumberBuilder::init(
    'number8'
)
    ->type('type0')
    ->build();
```

