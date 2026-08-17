
# Uninstall Android App Details

## Structure

`UninstallAndroidAppDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appId` | `?string` | Optional | The unique identifier of the app to be uninstalled. | getAppId(): ?string | setAppId(?string appId): void |
| `type` | [`?string(Type71Enum)`](../../doc/models/type-71-enum.md) | Optional | Type of terminal action: Uninstall an Android app.<br><br>**Default**: `Type71Enum::UNINSTALLANDROIDAPP` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\UninstallAndroidAppDetailsBuilder;
use AdyenLib\Models\Type71Enum;

$uninstallAndroidAppDetails = UninstallAndroidAppDetailsBuilder::init()
    ->appId('appId0')
    ->type(Type71Enum::UNINSTALLANDROIDAPP)
    ->build();
```

