
# Google Pay Response Info

## Structure

`GooglePayResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantId` | `?string` | Optional | Google Pay [Merchant ID] | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `reuseMerchantId` | `?bool` | Optional | Indicates whether the Google Pay Merchant ID is used for several merchant accounts. | getReuseMerchantId(): ?bool | setReuseMerchantId(?bool reuseMerchantId): void |

## Example

```php
use AdyenLib\Models\Builders\GooglePayResponseInfoBuilder;

$googlePayResponseInfo = GooglePayResponseInfoBuilder::init()
    ->merchantId('merchantId4')
    ->reuseMerchantId(false)
    ->build();
```

