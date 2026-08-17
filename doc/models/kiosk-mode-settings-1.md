
# Kiosk Mode Settings 1

Settings for kiosk mode.

## Structure

`KioskModeSettings1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedAppsInKioskMode` | `?(string[])` | Optional | List of package names for apps allowed to run in kiosk mode. | getAllowedAppsInKioskMode(): ?array | setAllowedAppsInKioskMode(?array allowedAppsInKioskMode): void |
| `kioskAppOnStartup` | `?string` | Optional | The package name of the app to launch on startup. This must be one of the apps included in `allowedAppsInKioskMode`. | getKioskAppOnStartup(): ?string | setKioskAppOnStartup(?string kioskAppOnStartup): void |

## Example

```php
use AdyenLib\Models\Builders\KioskModeSettings1Builder;

$kioskModeSettings1 = KioskModeSettings1Builder::init()
    ->allowedAppsInKioskMode(
        [
            'allowedAppsInKioskMode4',
            'allowedAppsInKioskMode5',
            'allowedAppsInKioskMode6'
        ]
    )
    ->kioskAppOnStartup('kioskAppOnStartup0')
    ->build();
```

