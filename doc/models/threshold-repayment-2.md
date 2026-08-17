
# Threshold Repayment 2

An object containing the details of the 30-day repayment threshold.

## Structure

`ThresholdRepayment2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount to be repaid on a 30-day basis. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\ThresholdRepayment2Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$thresholdRepayment2 = ThresholdRepayment2Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

