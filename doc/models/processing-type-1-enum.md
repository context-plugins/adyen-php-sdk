
# Processing Type 1 Enum

Contains information about how the payment was processed.

Possible values: **atmWithdraw**, **balanceInquiry**, **ecommerce**, **moto**, **pos**, **purchaseWithCashback**, **recurring**, **token**.

## Enumeration

`ProcessingType1Enum`

## Fields

| Name |
|  --- |
| `ATMWITHDRAW` |
| `BALANCEINQUIRY` |
| `ECOMMERCE` |
| `MOTO` |
| `POS` |
| `PURCHASEWITHCASHBACK` |
| `RECURRING` |
| `TOKEN` |

## Example

```php
use AdyenLib\Models\ProcessingType1Enum;

$processingType1 = ProcessingType1Enum::POS;
```

