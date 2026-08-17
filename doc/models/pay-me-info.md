
# Pay Me Info

## Structure

`PayMeInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayName` | `string` | Required | Merchant display name | getDisplayName(): string | setDisplayName(string displayName): void |
| `logo` | `string` | Required | Merchant logo. Format: Base64-encoded string. | getLogo(): string | setLogo(string logo): void |
| `supportEmail` | `string` | Required | The email address of merchant support. | getSupportEmail(): string | setSupportEmail(string supportEmail): void |

## Example

```php
use AdyenLib\Models\Builders\PayMeInfoBuilder;

$payMeInfo = PayMeInfoBuilder::init(
    'displayName4',
    'logo4',
    'supportEmail4'
)->build();
```

