
# Finish Sca Device Registration Response

## Structure

`FinishScaDeviceRegistrationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `scaDevice` | [`?ScaDevice`](../../doc/models/sca-device.md) | Optional | A resource that contains information about a device, including its unique ID, name, and type. | getScaDevice(): ?ScaDevice | setScaDevice(?ScaDevice scaDevice): void |

## Example

```php
use AdyenLib\Models\Builders\FinishScaDeviceRegistrationResponseBuilder;
use AdyenLib\Models\Builders\ScaDeviceBuilder;
use AdyenLib\Models\ScaDeviceType1Enum;

$finishScaDeviceRegistrationResponse = FinishScaDeviceRegistrationResponseBuilder::init()
    ->scaDevice(
        ScaDeviceBuilder::init(
            'id2',
            'name2',
            ScaDeviceType1Enum::BROWSER
        )->build()
    )->build();
```

