
# Sca Device

A resource that contains information about a device, including its unique ID, name, and type.

## Structure

`ScaDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The unique identifier of the SCA device you are registering. | getId(): string | setId(string id): void |
| `name` | `string` | Required | The name of the SCA device that you are registering. You can use it to help your users identify the device.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `64` | getName(): string | setName(string name): void |
| `type` | [`string(ScaDeviceType1Enum)`](../../doc/models/sca-device-type-1-enum.md) | Required | Type of device registered.<br><br>Possible values: **ios**, **android**, **browser**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\ScaDeviceBuilder;
use AdyenLib\Models\ScaDeviceType1Enum;

$scaDevice = ScaDeviceBuilder::init(
    'id2',
    'name2',
    ScaDeviceType1Enum::BROWSER
)->build();
```

