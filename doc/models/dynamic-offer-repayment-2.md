
# Dynamic Offer Repayment 2

Contains information about the repayment configuration of the grant.

## Structure

`DynamicOfferRepayment2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `term` | [`RepaymentTerm`](../../doc/models/repayment-term.md) | Required | Contains information about the time period in which your user must repay the total amount of the grant. | getTerm(): RepaymentTerm | setTerm(RepaymentTerm term): void |

## Example

```php
use AdyenLib\Models\Builders\DynamicOfferRepayment2Builder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;

$dynamicOfferRepayment2 = DynamicOfferRepayment2Builder::init(
    RepaymentTermBuilder::init(
        248
    )
        ->maximumDays(24)
        ->build()
)->build();
```

