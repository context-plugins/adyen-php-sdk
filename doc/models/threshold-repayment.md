
# Threshold Repayment

## Structure

`ThresholdRepayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount to be repaid on a 30-day basis. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\ThresholdRepaymentBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$thresholdRepayment = ThresholdRepaymentBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

