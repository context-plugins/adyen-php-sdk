
# Threshold Repayment 21

Contains the minimum threshold amount that your user must repay every 30-day period.

## Structure

`ThresholdRepayment21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The minimum threshold amount that your user must repay on every 30-day period. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\ThresholdRepayment21Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$thresholdRepayment21 = ThresholdRepayment21Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

