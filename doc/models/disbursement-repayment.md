
# Disbursement Repayment

## Structure

`DisbursementRepayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `basisPoints` | `int` | Required | The percentage of your user's incoming net volume that is deducted for repaying the grant. The percentage expressed in [basis points](https://www.investopedia.com/terms/b/basispoint.asp).<br><br>**Constraints**: `>= 0`, `<= 10000` | getBasisPoints(): int | setBasisPoints(int basisPoints): void |
| `updateDescription` | `string` | Required | **Constraints**: *Minimum Length*: `1`, *Maximum Length*: `240` | getUpdateDescription(): string | setUpdateDescription(string updateDescription): void |

## Example

```php
use AdyenLib\Models\Builders\DisbursementRepaymentBuilder;

$disbursementRepayment = DisbursementRepaymentBuilder::init(
    28,
    'updateDescription2'
)->build();
```

