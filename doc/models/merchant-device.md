
# Merchant Device

Merchant device information.

## Structure

`MerchantDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `os` | `?string` | Optional | Operating system running on the merchant device. | getOs(): ?string | setOs(?string os): void |
| `osVersion` | `?string` | Optional | Version of the operating system on the merchant device. | getOsVersion(): ?string | setOsVersion(?string osVersion): void |
| `reference` | `?string` | Optional | Merchant device reference. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantDeviceBuilder;

$merchantDevice = MerchantDeviceBuilder::init()
    ->os('os4')
    ->osVersion('osVersion6')
    ->reference('reference8')
    ->build();
```

