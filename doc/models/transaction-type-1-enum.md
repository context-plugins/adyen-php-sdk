
# Transaction Type 1 Enum

Possible values:

* **Debit**
* **Credit**
* **ReverseDebit**
* **ReverseCredit**
* **OneTimeReservation**
* **CompletedDeffered**
* **FirstReservation**
* **UpdateReservation**
* **CompletedReservation**
* **CashAdvance**
* **IssuerInstalment**
* **Declined**
* **Failed**
* **Award**
* **ReverseAward**
* **Redemption**
* **ReverseRedemption**
* **Rebate**
* **ReverseRebate**

## Enumeration

`TransactionType1Enum`

## Fields

| Name |
|  --- |
| `DEBIT` |
| `CREDIT` |
| `REVERSEDEBIT` |
| `REVERSECREDIT` |
| `ONETIMERESERVATION` |
| `COMPLETEDDEFFERED` |
| `FIRSTRESERVATION` |
| `UPDATERESERVATION` |
| `COMPLETEDRESERVATION` |
| `CASHADVANCE` |
| `ISSUERINSTALMENT` |
| `DECLINED` |
| `FAILED` |
| `AWARD` |
| `REVERSEAWARD` |
| `REDEMPTION` |
| `REVERSEREDEMPTION` |
| `REBATE` |
| `REVERSEREBATE` |

## Example

```php
use AdyenLib\Models\TransactionType1Enum;

$transactionType1 = TransactionType1Enum::COMPLETEDRESERVATION;
```

