
# Phone 11

The phone number where the one-time password (OTP) is sent.

This object must have:

* A `type` set to **mobile**.

* A `number` with a valid country code.

* A `number` with more than 4 digits, excluding the country code.

> Make sure to verify that the card user owns the phone number.

## Structure

`Phone11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `string` | Required | The full phone number provided as a single string.<br>For example, **"0031 6 11 22 33 44"**, **"+316/1122-3344"**,<br><br>or **"(0031) 611223344"**. | getNumber(): string | setNumber(string number): void |
| `type` | [`string(Type410Enum)`](../../doc/models/type-410-enum.md) | Required | Type of phone number.<br>Possible values:<br>**Landline**, **Mobile**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\Phone11Builder;
use AdyenLib\Models\Type410Enum;

$phone11 = Phone11Builder::init(
    'number0',
    Type410Enum::LANDLINE
)->build();
```

