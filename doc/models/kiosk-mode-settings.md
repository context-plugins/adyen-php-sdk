
# Kiosk Mode Settings

## Structure

`KioskModeSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedAppsInKioskMode` | `?(string[])` | Optional | List of package names for apps allowed to run in kiosk mode. | getAllowedAppsInKioskMode(): ?array | setAllowedAppsInKioskMode(?array allowedAppsInKioskMode): void |
| `kioskAppOnStartup` | `?string` | Optional | The package name of the app to launch on startup. This must be one of the apps included in `allowedAppsInKioskMode`. | getKioskAppOnStartup(): ?string | setKioskAppOnStartup(?string kioskAppOnStartup): void |

## Example

```php
use AdyenLib\Models\Builders\KioskModeSettingsBuilder;

$kioskModeSettings = KioskModeSettingsBuilder::init()
    ->allowedAppsInKioskMode(
        [
            'allowedAppsInKioskMode8',
            'allowedAppsInKioskMode9'
        ]
    )
    ->kioskAppOnStartup('kioskAppOnStartup6')
    ->build();
```

