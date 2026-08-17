
# Instalment

## Structure

`Instalment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `instalmentType` | [`?string(InstalmentTypeEnum)`](../../doc/models/instalment-type-enum.md) | Optional | Type of instalment transaction. For requesting an instalment payment transaction.<br>Possible values:<br><br>* **DeferredInstalments**<br>* **EqualInstalments**<br>* **InequalInstalments** | getInstalmentType(): ?string | setInstalmentType(?string instalmentType): void |
| `sequenceNumber` | `?int` | Optional | Sequence number of the instalment. For an instalment payment transaction, number of the payment, from 1 to TotalNbOfPayments. | getSequenceNumber(): ?int | setSequenceNumber(?int sequenceNumber): void |
| `planID` | `?string` | Optional | Identification of an instalment plan.<br><br>**Constraints**: *Pattern*: `^.+$` | getPlanID(): ?string | setPlanID(?string planID): void |
| `period` | `?int` | Optional | Period of time with defined unit of time. A period between 2 payment instalments. | getPeriod(): ?int | setPeriod(?int period): void |
| `periodUnit` | [`?string(PeriodUnit1Enum)`](../../doc/models/period-unit-1-enum.md) | Optional | Type of instalment transaction.<br>Possible values:<br><br>* **Annual**<br>* **Daily**<br>* **Monthly**<br>* **Weekly** | getPeriodUnit(): ?string | setPeriodUnit(?string periodUnit): void |
| `firstPaymentDate` | `?DateTime` | Optional | First date of a payment. For instalment, the date of the first payments, if not immediate. | getFirstPaymentDate(): ?\DateTime | setFirstPaymentDate(?\DateTime firstPaymentDate): void |
| `totalNbOfPayments` | `?int` | Optional | Total number of payments. For instalment, the number of payments, including the first one. | getTotalNbOfPayments(): ?int | setTotalNbOfPayments(?int totalNbOfPayments): void |
| `cumulativeAmount` | `?float` | Optional | Sum of a collection of amounts. Total amount of the payment instalments.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCumulativeAmount(): ?float | setCumulativeAmount(?float cumulativeAmount): void |
| `firstAmount` | `?float` | Optional | First amount of the payment instalments.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getFirstAmount(): ?float | setFirstAmount(?float firstAmount): void |
| `charges` | `?float` | Optional | Charges related to a transaction. Charge related to the payment instalments.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCharges(): ?float | setCharges(?float charges): void |

## Example

```php
use AdyenLib\Models\Builders\InstalmentBuilder;
use AdyenLib\Models\InstalmentTypeEnum;
use AdyenLib\Models\PeriodUnit1Enum;

$instalment = InstalmentBuilder::init()
    ->instalmentType(InstalmentTypeEnum::DEFERREDINSTALMENTS)
    ->sequenceNumber(164)
    ->planID('PlanID4')
    ->period(56)
    ->periodUnit(PeriodUnit1Enum::DAILY)
    ->build();
```

