
# App Identifier Info

## Structure

`AppIdentifierInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `androidPackageId` | `?string` | Optional | The Android package identifier for this app. | getAndroidPackageId(): ?string | setAndroidPackageId(?string androidPackageId): void |
| `iosScheme` | `?string` | Optional | The iOS URL scheme for this app. | getIosScheme(): ?string | setIosScheme(?string iosScheme): void |

## Example

```php
use AdyenLib\Models\Builders\AppIdentifierInfoBuilder;

$appIdentifierInfo = AppIdentifierInfoBuilder::init()
    ->androidPackageId('androidPackageId8')
    ->iosScheme('iosScheme8')
    ->build();
```

