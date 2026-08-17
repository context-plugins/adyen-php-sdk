
# Afterpay Touch Response Info

## Structure

`AfterpayTouchResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportEmail` | `?string` | Optional | Support Email | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |
| `supportUrl` | `?string` | Optional | Support Url | getSupportUrl(): ?string | setSupportUrl(?string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\AfterpayTouchResponseInfoBuilder;

$afterpayTouchResponseInfo = AfterpayTouchResponseInfoBuilder::init()
    ->supportEmail('supportEmail0')
    ->supportUrl('supportUrl4')
    ->build();
```

