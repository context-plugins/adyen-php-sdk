
# Begin Sca Device Registration Response

## Structure

`BeginScaDeviceRegistrationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `scaDevice` | [`?ScaDevice`](../../doc/models/sca-device.md) | Optional | A resource that contains information about a device, including its unique ID, name, and type. | getScaDevice(): ?ScaDevice | setScaDevice(?ScaDevice scaDevice): void |
| `sdkInput` | `?string` | Optional | A string that you must pass to the authentication SDK to continue with the registration process.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkInput(): ?string | setSdkInput(?string sdkInput): void |

## Example

```php
use AdyenLib\Models\Builders\BeginScaDeviceRegistrationResponseBuilder;
use AdyenLib\Models\Builders\ScaDeviceBuilder;
use AdyenLib\Models\ScaDeviceType1Enum;

$beginScaDeviceRegistrationResponse = BeginScaDeviceRegistrationResponseBuilder::init()
    ->scaDevice(
        ScaDeviceBuilder::init(
            'id2',
            'name2',
            ScaDeviceType1Enum::BROWSER
        )->build()
    )
    ->sdkInput('sdkInput4')
    ->build();
```

