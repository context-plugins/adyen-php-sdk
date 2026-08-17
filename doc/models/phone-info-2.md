
# Phone Info 2

The information about the phone number of the device used to provision the the network token. This object is conditionally returned and is available for up to 24 hours after the provisioning request (access to this field requires a specific user role, please contact your Adyen representative to request permission).

## Structure

`PhoneInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hashedNumber` | `?string` | Optional | The hashed value of the phone number used to provision the network token. | getHashedNumber(): ?string | setHashedNumber(?string hashedNumber): void |
| `lastFourDigits` | `?string` | Optional | The last four digits of the phone number used to provision the network token. | getLastFourDigits(): ?string | setLastFourDigits(?string lastFourDigits): void |
| `number` | `?string` | Optional | The full phone number of the device used to provision the network token. | getNumber(): ?string | setNumber(?string number): void |

## Example

```php
use AdyenLib\Models\Builders\PhoneInfo2Builder;

$phoneInfo2 = PhoneInfo2Builder::init()
    ->hashedNumber('hashedNumber0')
    ->lastFourDigits('lastFourDigits0')
    ->number('number0')
    ->build();
```

