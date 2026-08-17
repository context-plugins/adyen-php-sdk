
# Pay Me Response Info 1

**payme** details

## Structure

`PayMeResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayName` | `?string` | Optional | Merchant display name | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `logo` | `?string` | Optional | Merchant logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |
| `supportEmail` | `?string` | Optional | The email address of merchant support. | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |

## Example

```php
use AdyenLib\Models\Builders\PayMeResponseInfo1Builder;

$payMeResponseInfo1 = PayMeResponseInfo1Builder::init()
    ->displayName('displayName0')
    ->logo('logo8')
    ->supportEmail('supportEmail8')
    ->build();
```

