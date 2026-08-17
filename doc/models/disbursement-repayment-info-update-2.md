
# Disbursement Repayment Info Update 2

Contains information about the basis points configured for repaying the disbursement.

## Structure

`DisbursementRepaymentInfoUpdate2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `basisPoints` | `?int` | Optional | The percentage of your user's incoming net volume that is deducted for repaying the grant. The percentage expressed in [basis points](https://www.investopedia.com/terms/b/basispoint.asp).<br><br>**Constraints**: `>= 0`, `<= 10000` | getBasisPoints(): ?int | setBasisPoints(?int basisPoints): void |
| `updateDescription` | `?string` | Optional | **Constraints**: *Minimum Length*: `0`, *Maximum Length*: `240` | getUpdateDescription(): ?string | setUpdateDescription(?string updateDescription): void |

## Example

```php
use AdyenLib\Models\Builders\DisbursementRepaymentInfoUpdate2Builder;

$disbursementRepaymentInfoUpdate2 = DisbursementRepaymentInfoUpdate2Builder::init()
    ->basisPoints(152)
    ->updateDescription('updateDescription8')
    ->build();
```

