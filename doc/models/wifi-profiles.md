
# Wifi Profiles

## Structure

`WifiProfiles`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `profiles` | [`?(Profile[])`](../../doc/models/profile.md) | Optional | List of remote Wi-Fi profiles. | getProfiles(): ?array | setProfiles(?array profiles): void |
| `settings` | [`?Settings1`](../../doc/models/settings-1.md) | Optional | General Wi-Fi settings. | getSettings(): ?Settings1 | setSettings(?Settings1 settings): void |

## Example

```php
use AdyenLib\Models\Builders\WifiProfilesBuilder;
use AdyenLib\Models\Builders\ProfileBuilder;
use AdyenLib\Models\Builders\Settings1Builder;

$wifiProfiles = WifiProfilesBuilder::init()
    ->profiles(
        [
            ProfileBuilder::init(
                'authType8',
                'bssType4',
                'ssid6',
                'wsec4'
            )
                ->autoWifi(false)
                ->channel(198)
                ->defaultProfile(false)
                ->domainSuffix('domainSuffix2')
                ->eap('eap0')
                ->build()
        ]
    )
    ->settings(
        Settings1Builder::init()
            ->band('band0')
            ->roaming(false)
            ->timeout(124)
            ->build()
    )
    ->build();
```

