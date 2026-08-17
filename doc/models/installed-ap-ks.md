
# Installed AP Ks

## Structure

`InstalledAPKs`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `confirmationDate` | `?DateTime` | Optional | The date and time when the app was installed. | getConfirmationDate(): ?\DateTime | setConfirmationDate(?\DateTime confirmationDate): void |
| `packageName` | `?string` | Optional | The package name of the app. | getPackageName(): ?string | setPackageName(?string packageName): void |
| `versionName` | `?string` | Optional | The version name of the app. | getVersionName(): ?string | setVersionName(?string versionName): void |

## Example

```php
use AdyenLib\Models\Builders\InstalledAPKsBuilder;
use AdyenLib\Utils\DateTimeHelper;

$installedAPKs = InstalledAPKsBuilder::init()
    ->confirmationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->packageName('packageName6')
    ->versionName('versionName6')
    ->build();
```

