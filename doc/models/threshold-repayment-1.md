
# Threshold Repayment 1

## Structure

`ThresholdRepayment1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The minimum threshold amount that your user must repay on every 30-day period. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\ThresholdRepayment1Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$thresholdRepayment1 = ThresholdRepayment1Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

