
# Afterpay Touch Response Info 1

**afterpaytouch** details

## Structure

`AfterpayTouchResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportEmail` | `?string` | Optional | Support Email | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |
| `supportUrl` | `?string` | Optional | Support Url | getSupportUrl(): ?string | setSupportUrl(?string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\AfterpayTouchResponseInfo1Builder;

$afterpayTouchResponseInfo1 = AfterpayTouchResponseInfo1Builder::init()
    ->supportEmail('supportEmail6')
    ->supportUrl('supportUrl2')
    ->build();
```

