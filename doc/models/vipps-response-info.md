
# Vipps Response Info

## Structure

`VippsResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logo` | `?string` | Optional | Vipps logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |
| `subscriptionCancelUrl` | `?string` | Optional | Vipps subscription cancel url (required in case of [recurring payments](https://docs.adyen.com/online-payments/tokenization)) | getSubscriptionCancelUrl(): ?string | setSubscriptionCancelUrl(?string subscriptionCancelUrl): void |

## Example

```php
use AdyenLib\Models\Builders\VippsResponseInfoBuilder;

$vippsResponseInfo = VippsResponseInfoBuilder::init()
    ->logo('logo6')
    ->subscriptionCancelUrl('subscriptionCancelUrl8')
    ->build();
```

