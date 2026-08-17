
# Healthcare

## Structure

`Healthcare`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dentalValue` | `?int` | Optional | The dental amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000 | getDentalValue(): ?int | setDentalValue(?int dentalValue): void |
| `otherMedicalValue` | `?int` | Optional | The other medical amount not covered by the specific categories, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000 | getOtherMedicalValue(): ?int | setOtherMedicalValue(?int otherMedicalValue): void |
| `prescriptionValue` | `?int` | Optional | The prescription/Rx amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000 | getPrescriptionValue(): ?int | setPrescriptionValue(?int prescriptionValue): void |
| `totalHealthcareValue` | `int` | Required | The total healthcare amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000 | getTotalHealthcareValue(): int | setTotalHealthcareValue(int totalHealthcareValue): void |
| `visionPrescriptionValue` | `?int` | Optional | The vision/optical prescription amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000 | getVisionPrescriptionValue(): ?int | setVisionPrescriptionValue(?int visionPrescriptionValue): void |

## Example

```php
use AdyenLib\Models\Builders\HealthcareBuilder;

$healthcare = HealthcareBuilder::init(
    16
)
    ->dentalValue(132)
    ->otherMedicalValue(150)
    ->prescriptionValue(116)
    ->visionPrescriptionValue(166)
    ->build();
```

