
# Dynamic Offer Repayment

## Structure

`DynamicOfferRepayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `term` | [`RepaymentTerm`](../../doc/models/repayment-term.md) | Required | Contains information about the time period in which your user must repay the total amount of the grant. | getTerm(): RepaymentTerm | setTerm(RepaymentTerm term): void |

## Example

```php
use AdyenLib\Models\Builders\DynamicOfferRepaymentBuilder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;

$dynamicOfferRepayment = DynamicOfferRepaymentBuilder::init(
    RepaymentTermBuilder::init(
        248
    )
        ->maximumDays(24)
        ->build()
)->build();
```

