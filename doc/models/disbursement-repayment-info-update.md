
# Disbursement Repayment Info Update

## Structure

`DisbursementRepaymentInfoUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `basisPoints` | `?int` | Optional | The percentage of your user's incoming net volume that is deducted for repaying the grant. The percentage expressed in [basis points](https://www.investopedia.com/terms/b/basispoint.asp).<br><br>**Constraints**: `>= 0`, `<= 10000` | getBasisPoints(): ?int | setBasisPoints(?int basisPoints): void |
| `updateDescription` | `?string` | Optional | **Constraints**: *Minimum Length*: `0`, *Maximum Length*: `240` | getUpdateDescription(): ?string | setUpdateDescription(?string updateDescription): void |

## Example

```php
use AdyenLib\Models\Builders\DisbursementRepaymentInfoUpdateBuilder;

$disbursementRepaymentInfoUpdate = DisbursementRepaymentInfoUpdateBuilder::init()
    ->basisPoints(234)
    ->updateDescription('updateDescription6')
    ->build();
```

