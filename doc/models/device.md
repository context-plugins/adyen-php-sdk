
# Device

## Structure

`Device`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the SCA device. | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | The name of the SCA device. You can show this name to your user to help them identify the device. | getName(): ?string | setName(?string name): void |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the payment instrument that is associated with the SCA device. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |
| `type` | [`?string(Type101Enum)`](../../doc/models/type-101-enum.md) | Optional | The type of device.<br><br>Possible values: **ios**, **android**, **browser**. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\DeviceBuilder;
use AdyenLib\Models\Type101Enum;

$device = DeviceBuilder::init()
    ->id('id6')
    ->name('name6')
    ->paymentInstrumentId('paymentInstrumentId8')
    ->type(Type101Enum::IOS)
    ->build();
```

