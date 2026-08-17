
# Phone Info

## Structure

`PhoneInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hashedNumber` | `?string` | Optional | The hashed value of the phone number used to provision the network token. | getHashedNumber(): ?string | setHashedNumber(?string hashedNumber): void |
| `lastFourDigits` | `?string` | Optional | The last four digits of the phone number used to provision the network token. | getLastFourDigits(): ?string | setLastFourDigits(?string lastFourDigits): void |
| `number` | `?string` | Optional | The full phone number of the device used to provision the network token. | getNumber(): ?string | setNumber(?string number): void |

## Example

```php
use AdyenLib\Models\Builders\PhoneInfoBuilder;

$phoneInfo = PhoneInfoBuilder::init()
    ->hashedNumber('hashedNumber6')
    ->lastFourDigits('lastFourDigits4')
    ->number('number6')
    ->build();
```

