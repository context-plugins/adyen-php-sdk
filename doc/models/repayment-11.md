
# Repayment 11

Contains information about the repayment configuration of the grant.

## Structure

`Repayment11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `basisPoints` | `int` | Required | The percentage of your user's incoming net volume that is deducted for repaying the grant. The percentage expressed in [basis points](https://www.investopedia.com/terms/b/basispoint.asp). | getBasisPoints(): int | setBasisPoints(int basisPoints): void |
| `term` | [`?RepaymentTerm`](../../doc/models/repayment-term.md) | Optional | Contains information about the time period in which your user must repay the total amount of the grant. | getTerm(): ?RepaymentTerm | setTerm(?RepaymentTerm term): void |
| `threshold` | [`?ThresholdRepayment21`](../../doc/models/threshold-repayment-21.md) | Optional | Contains the minimum threshold amount that your user must repay every 30-day period. | getThreshold(): ?ThresholdRepayment21 | setThreshold(?ThresholdRepayment21 threshold): void |

## Example

```php
use AdyenLib\Models\Builders\Repayment11Builder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;
use AdyenLib\Models\Builders\ThresholdRepayment21Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$repayment11 = Repayment11Builder::init(
    238
)
    ->term(
        RepaymentTermBuilder::init(
            248
        )
            ->maximumDays(24)
            ->build()
    )
    ->threshold(
        ThresholdRepayment21Builder::init(
            Amount17Builder::init(
                'currency2',
                110
            )->build()
        )->build()
    )->build();
```

