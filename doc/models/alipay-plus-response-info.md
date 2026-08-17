
# Alipay plus Response Info

## Structure

`AlipayPlusResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `settlementCurrencyCode` | `?string` | Optional | The currency used for settlement. | getSettlementCurrencyCode(): ?string | setSettlementCurrencyCode(?string settlementCurrencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\AlipayPlusResponseInfoBuilder;

$alipayPlusResponseInfo = AlipayPlusResponseInfoBuilder::init()
    ->settlementCurrencyCode('settlementCurrencyCode4')
    ->build();
```

