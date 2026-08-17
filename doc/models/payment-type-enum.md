
# Payment Type Enum

Possible values:

* **Normal**
* **Refund**
* **OneTimeReservation**
* **FirstReservation**
* **UpdateReservation**
* **Completion**
* **CashAdvance**
* **CashDeposit**
* **Recurring**
* **Instalment**
* **IssuerInstalment**
* **PaidOut**

## Enumeration

`PaymentTypeEnum`

## Fields

| Name |
|  --- |
| `NORMAL` |
| `REFUND` |
| `ONETIMERESERVATION` |
| `FIRSTRESERVATION` |
| `UPDATERESERVATION` |
| `COMPLETION` |
| `CASHADVANCE` |
| `CASHDEPOSIT` |
| `RECURRING` |
| `INSTALMENT` |
| `ISSUERINSTALMENT` |
| `PAIDOUT` |

## Example

```php
use AdyenLib\Models\PaymentTypeEnum;

$paymentType = PaymentTypeEnum::UPDATERESERVATION;
```

