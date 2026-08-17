
# Google Pay Response Info 1

**googlepay** details

## Structure

`GooglePayResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantId` | `?string` | Optional | Google Pay [Merchant ID] | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `reuseMerchantId` | `?bool` | Optional | Indicates whether the Google Pay Merchant ID is used for several merchant accounts. | getReuseMerchantId(): ?bool | setReuseMerchantId(?bool reuseMerchantId): void |

## Example

```php
use AdyenLib\Models\Builders\GooglePayResponseInfo1Builder;

$googlePayResponseInfo1 = GooglePayResponseInfo1Builder::init()
    ->merchantId('merchantId6')
    ->reuseMerchantId(false)
    ->build();
```

