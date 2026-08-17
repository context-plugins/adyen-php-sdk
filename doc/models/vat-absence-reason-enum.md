
# Vat Absence Reason Enum

The reason the organization has not provided a VAT number.

Possible values: **industryExemption**, **belowTaxThreshold**.

## Enumeration

`VatAbsenceReasonEnum`

## Fields

| Name |
|  --- |
| `INDUSTRYEXEMPTION` |
| `BELOWTAXTHRESHOLD` |

## Example

```php
use AdyenLib\Models\VatAbsenceReasonEnum;

$vatAbsenceReason = VatAbsenceReasonEnum::INDUSTRYEXEMPTION;
```

