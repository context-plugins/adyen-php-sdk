
# Device Info 1

Contains information about the device used to provision the network token.

## Structure

`DeviceInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `formFactor` | `?string` | Optional | The type of device used to provision the network token. | getFormFactor(): ?string | setFormFactor(?string formFactor): void |
| `osName` | `?string` | Optional | The operating system of the device used to provision the network token. | getOsName(): ?string | setOsName(?string osName): void |
| `phone` | [`?PhoneInfo2`](../../doc/models/phone-info-2.md) | Optional | The information about the phone number of the device used to provision the the network token. This object is conditionally returned and is available for up to 24 hours after the provisioning request (access to this field requires a specific user role, please contact your Adyen representative to request permission). | getPhone(): ?PhoneInfo2 | setPhone(?PhoneInfo2 phone): void |

## Example

```php
use AdyenLib\Models\Builders\DeviceInfo1Builder;
use AdyenLib\Models\Builders\PhoneInfo2Builder;

$deviceInfo1 = DeviceInfo1Builder::init()
    ->formFactor('formFactor0')
    ->osName('osName0')
    ->phone(
        PhoneInfo2Builder::init()
            ->hashedNumber('hashedNumber2')
            ->lastFourDigits('lastFourDigits8')
            ->number('number8')
            ->build()
    )
    ->build();
```

