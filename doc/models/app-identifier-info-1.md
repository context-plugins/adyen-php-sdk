
# App Identifier Info 1

The app identifier information containing iOS scheme and Android package ID.

## Structure

`AppIdentifierInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `androidPackageId` | `?string` | Optional | The Android package identifier for this app. | getAndroidPackageId(): ?string | setAndroidPackageId(?string androidPackageId): void |
| `iosScheme` | `?string` | Optional | The iOS URL scheme for this app. | getIosScheme(): ?string | setIosScheme(?string iosScheme): void |

## Example

```php
use AdyenLib\Models\Builders\AppIdentifierInfo1Builder;

$appIdentifierInfo1 = AppIdentifierInfo1Builder::init()
    ->androidPackageId('androidPackageId2')
    ->iosScheme('iosScheme2')
    ->build();
```

