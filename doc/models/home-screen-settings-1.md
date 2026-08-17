
# Home Screen Settings 1

Settings for the home screen.

## Structure

`HomeScreenSettings1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hideNavigationBar` | `?bool` | Optional | Hide/show the navigation bar. | getHideNavigationBar(): ?bool | setHideNavigationBar(?bool hideNavigationBar): void |
| `showPaymentsMenu` | `?bool` | Optional | Show/hide the payments menu. | getShowPaymentsMenu(): ?bool | setShowPaymentsMenu(?bool showPaymentsMenu): void |
| `showSettingsMenu` | `?bool` | Optional | Show/hide the settings menu. | getShowSettingsMenu(): ?bool | setShowSettingsMenu(?bool showSettingsMenu): void |

## Example

```php
use AdyenLib\Models\Builders\HomeScreenSettings1Builder;

$homeScreenSettings1 = HomeScreenSettings1Builder::init()
    ->hideNavigationBar(false)
    ->showPaymentsMenu(false)
    ->showSettingsMenu(false)
    ->build();
```

