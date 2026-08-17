
# Shopper Interaction Device

Shopper interaction device, such as terminal, mobile device or web browser, to initiate payment requests.

## Structure

`ShopperInteractionDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locale` | `?string` | Optional | Locale on the shopper interaction device. | getLocale(): ?string | setLocale(?string locale): void |
| `os` | `?string` | Optional | Operating system running on the shopper interaction device. | getOs(): ?string | setOs(?string os): void |
| `osVersion` | `?string` | Optional | Version of the operating system on the shopper interaction device. | getOsVersion(): ?string | setOsVersion(?string osVersion): void |

## Example

```php
use AdyenLib\Models\Builders\ShopperInteractionDeviceBuilder;

$shopperInteractionDevice = ShopperInteractionDeviceBuilder::init()
    ->locale('locale2')
    ->os('os2')
    ->osVersion('osVersion4')
    ->build();
```

