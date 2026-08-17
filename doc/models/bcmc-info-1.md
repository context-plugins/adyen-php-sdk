
# Bcmc Info 1

Details to provide if `type` is **bcmc** (Bancontact).

## Structure

`BcmcInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enableBcmcMobile` | `?bool` | Optional | Indicates if [Bancontact mobile](https://docs.adyen.com/payment-methods/bancontact/bancontact-mobile) is enabled. | getEnableBcmcMobile(): ?bool | setEnableBcmcMobile(?bool enableBcmcMobile): void |

## Example

```php
use AdyenLib\Models\Builders\BcmcInfo1Builder;

$bcmcInfo1 = BcmcInfo1Builder::init()
    ->enableBcmcMobile(false)
    ->build();
```

