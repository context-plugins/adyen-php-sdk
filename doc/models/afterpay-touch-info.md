
# Afterpay Touch Info

## Structure

`AfterpayTouchInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportEmail` | `?string` | Optional | Support Email | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |
| `supportUrl` | `string` | Required | Support Url | getSupportUrl(): string | setSupportUrl(string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\AfterpayTouchInfoBuilder;

$afterpayTouchInfo = AfterpayTouchInfoBuilder::init(
    'supportUrl4'
)
    ->supportEmail('supportEmail8')
    ->build();
```

