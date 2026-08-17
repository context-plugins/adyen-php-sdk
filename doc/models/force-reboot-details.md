
# Force Reboot Details

## Structure

`ForceRebootDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | [`?string(Type210Enum)`](../../doc/models/type-210-enum.md) | Optional | The type of terminal action. The value **ForceReboot** triggers an immediate reboot of the specified terminal(s).<br><br>**Default**: `Type210Enum::FORCEREBOOT` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\ForceRebootDetailsBuilder;
use AdyenLib\Models\Type210Enum;

$forceRebootDetails = ForceRebootDetailsBuilder::init()
    ->type(Type210Enum::FORCEREBOOT)
    ->build();
```

