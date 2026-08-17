
# Vipps Info 2

Details to provide if `type` is **vipps**.

## Structure

`VippsInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logo` | `string` | Required | Vipps logo. Format: Base64-encoded string. | getLogo(): string | setLogo(string logo): void |
| `subscriptionCancelUrl` | `?string` | Optional | Vipps subscription cancel url (required in case of [recurring payments](https://docs.adyen.com/online-payments/tokenization)) | getSubscriptionCancelUrl(): ?string | setSubscriptionCancelUrl(?string subscriptionCancelUrl): void |

## Example

```php
use AdyenLib\Models\Builders\VippsInfo2Builder;

$vippsInfo2 = VippsInfo2Builder::init(
    'logo8'
)
    ->subscriptionCancelUrl('subscriptionCancelUrl4')
    ->build();
```

