
# Release Update Details

## Structure

`ReleaseUpdateDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | [`?string(Type61Enum)`](../../doc/models/type-61-enum.md) | Optional | Type of terminal action: Update Release.<br><br>**Default**: `Type61Enum::RELEASEUPDATE` | getType(): ?string | setType(?string type): void |
| `updateAtFirstMaintenanceCall` | `?bool` | Optional | Boolean flag that tells if the terminal should update at the first next maintenance call. If false, terminal will update on its configured reboot time. | getUpdateAtFirstMaintenanceCall(): ?bool | setUpdateAtFirstMaintenanceCall(?bool updateAtFirstMaintenanceCall): void |

## Example

```php
use AdyenLib\Models\Builders\ReleaseUpdateDetailsBuilder;
use AdyenLib\Models\Type61Enum;

$releaseUpdateDetails = ReleaseUpdateDetailsBuilder::init()
    ->type(Type61Enum::RELEASEUPDATE)
    ->updateAtFirstMaintenanceCall(false)
    ->build();
```

