
# Repayment

An object containing the details of the 30-day repayment threshold.

## Structure

`Repayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `basisPoints` | `int` | Required | The repayment that is deducted daily from incoming net volume, in [basis points](https://www.investopedia.com/terms/b/basispoint.asp). | getBasisPoints(): int | setBasisPoints(int basisPoints): void |
| `term` | [`?RepaymentTerm`](../../doc/models/repayment-term.md) | Optional | An object containing the details of the configuration for repayment term. | getTerm(): ?RepaymentTerm | setTerm(?RepaymentTerm term): void |
| `threshold` | [`?ThresholdRepayment2`](../../doc/models/threshold-repayment-2.md) | Optional | An object containing the details of the 30-day repayment threshold. | getThreshold(): ?ThresholdRepayment2 | setThreshold(?ThresholdRepayment2 threshold): void |

## Example

```php
use AdyenLib\Models\Builders\RepaymentBuilder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;
use AdyenLib\Models\Builders\ThresholdRepayment2Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$repayment = RepaymentBuilder::init(
    18
)
    ->term(
        RepaymentTermBuilder::init(
            248
        )
            ->maximumDays(24)
            ->build()
    )
    ->threshold(
        ThresholdRepayment2Builder::init(
            Amount17Builder::init(
                'currency2',
                110
            )->build()
        )->build()
    )->build();
```

