
# Repayment Term

An object containing the details of the configuration for repayment term., Contains information about the time period in which your user must repay the total amount of the grant.

## Structure

`RepaymentTerm`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `estimatedDays` | `int` | Required | The estimated term for repaying the grant, in days. | getEstimatedDays(): int | setEstimatedDays(int estimatedDays): void |
| `maximumDays` | `?int` | Optional | The maximum term for repaying the grant, in days. Only applies when `contractType` is **loan**. | getMaximumDays(): ?int | setMaximumDays(?int maximumDays): void |

## Example

```php
use AdyenLib\Models\Builders\RepaymentTermBuilder;

$repaymentTerm = RepaymentTermBuilder::init(
    34
)
    ->maximumDays(66)
    ->build();
```

