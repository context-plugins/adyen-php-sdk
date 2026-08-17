
# Install Android App Details

## Structure

`InstallAndroidAppDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appId` | `?string` | Optional | The unique identifier of the app to be installed. | getAppId(): ?string | setAppId(?string appId): void |
| `type` | [`?string(Type32Enum)`](../../doc/models/type-32-enum.md) | Optional | Type of terminal action: Install an Android app.<br><br>**Default**: `Type32Enum::INSTALLANDROIDAPP` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\InstallAndroidAppDetailsBuilder;
use AdyenLib\Models\Type32Enum;

$installAndroidAppDetails = InstallAndroidAppDetailsBuilder::init()
    ->appId('appId8')
    ->type(Type32Enum::INSTALLANDROIDAPP)
    ->build();
```

