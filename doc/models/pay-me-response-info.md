
# Pay Me Response Info

## Structure

`PayMeResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayName` | `?string` | Optional | Merchant display name | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `logo` | `?string` | Optional | Merchant logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |
| `supportEmail` | `?string` | Optional | The email address of merchant support. | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |

## Example

```php
use AdyenLib\Models\Builders\PayMeResponseInfoBuilder;

$payMeResponseInfo = PayMeResponseInfoBuilder::init()
    ->displayName('displayName6')
    ->logo('logo4')
    ->supportEmail('supportEmail4')
    ->build();
```

