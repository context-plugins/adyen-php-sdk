
# Cost Estimate Assumptions 1

Assumptions made for the expected characteristics of the transaction, for which the charges are being estimated.

## Structure

`CostEstimateAssumptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `assume3DSecureAuthenticated` | `?bool` | Optional | If true, the cardholder is expected to successfully authorise via 3D Secure. | getAssume3DSecureAuthenticated(): ?bool | setAssume3DSecureAuthenticated(?bool assume3DSecureAuthenticated): void |
| `assumeLevel3Data` | `?bool` | Optional | If true, the transaction is expected to have valid Level 3 data. | getAssumeLevel3Data(): ?bool | setAssumeLevel3Data(?bool assumeLevel3Data): void |
| `installments` | `?int` | Optional | If not zero, the number of installments. | getInstallments(): ?int | setInstallments(?int installments): void |

## Example

```php
use AdyenLib\Models\Builders\CostEstimateAssumptions1Builder;

$costEstimateAssumptions1 = CostEstimateAssumptions1Builder::init()
    ->assume3DSecureAuthenticated(false)
    ->assumeLevel3Data(false)
    ->installments(40)
    ->build();
```

