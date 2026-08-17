
# Disbursement Info Update

## Structure

`DisbursementInfoUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `repayment` | [`?DisbursementRepaymentInfoUpdate2`](../../doc/models/disbursement-repayment-info-update-2.md) | Optional | Contains information about the basis points configured for repaying the disbursement. | getRepayment(): ?DisbursementRepaymentInfoUpdate2 | setRepayment(?DisbursementRepaymentInfoUpdate2 repayment): void |

## Example

```php
use AdyenLib\Models\Builders\DisbursementInfoUpdateBuilder;
use AdyenLib\Models\Builders\DisbursementRepaymentInfoUpdate2Builder;

$disbursementInfoUpdate = DisbursementInfoUpdateBuilder::init()
    ->repayment(
        DisbursementRepaymentInfoUpdate2Builder::init()
            ->basisPoints(18)
            ->updateDescription('updateDescription0')
            ->build()
    )
    ->build();
```

