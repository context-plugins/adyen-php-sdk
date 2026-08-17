
# Alipay plus Response Info 1

**alipay_plus** details

## Structure

`AlipayPlusResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `settlementCurrencyCode` | `?string` | Optional | The currency used for settlement. | getSettlementCurrencyCode(): ?string | setSettlementCurrencyCode(?string settlementCurrencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\AlipayPlusResponseInfo1Builder;

$alipayPlusResponseInfo1 = AlipayPlusResponseInfo1Builder::init()
    ->settlementCurrencyCode('settlementCurrencyCode4')
    ->build();
```

