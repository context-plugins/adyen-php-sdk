
# Afterpay Touch Info 1

Details to provide if `type` is **afterpaytouch**.

## Structure

`AfterpayTouchInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportEmail` | `?string` | Optional | Support Email | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |
| `supportUrl` | `string` | Required | Support Url | getSupportUrl(): string | setSupportUrl(string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\AfterpayTouchInfo1Builder;

$afterpayTouchInfo1 = AfterpayTouchInfo1Builder::init(
    'supportUrl2'
)
    ->supportEmail('supportEmail6')
    ->build();
```

