
# Alipay plus Info

## Structure

`AlipayPlusInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `settlementCurrencyCode` | `?string` | Optional | The currency used for settlement. Defaults to USD. | getSettlementCurrencyCode(): ?string | setSettlementCurrencyCode(?string settlementCurrencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\AlipayPlusInfoBuilder;

$alipayPlusInfo = AlipayPlusInfoBuilder::init()
    ->settlementCurrencyCode('settlementCurrencyCode4')
    ->build();
```

