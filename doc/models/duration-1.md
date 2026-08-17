
# Duration 1

The duration, which you can specify in hours, days, weeks, or months. The maximum duration is 90 days or an equivalent in other units. Required when the `type` is **rolling** or **sliding**.

## Structure

`Duration1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `unit` | [`?string(UnitEnum)`](../../doc/models/unit-enum.md) | Optional | The unit of time. You can only use **minutes** and **hours** if the `interval.type` is **sliding**.<br><br>Possible values: **minutes**, **hours**, **days**, **weeks**, or **months** | getUnit(): ?string | setUnit(?string unit): void |
| `value` | `?int` | Optional | The length of time by the unit. For example, 5 days.<br><br>The maximum duration is 90 days or an equivalent in other units. For example, 3 months. | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\Duration1Builder;
use AdyenLib\Models\UnitEnum;

$duration1 = Duration1Builder::init()
    ->unit(UnitEnum::WEEKS)
    ->value(82)
    ->build();
```

