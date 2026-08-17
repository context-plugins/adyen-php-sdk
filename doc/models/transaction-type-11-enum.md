
# Transaction Type 11 Enum

Type of transaction for which totals are grouped.
Debit, Credit, ReverseDebit, ReverseCredit, OneTimeReservation, CompletedDeffered, FirstReservation, UpdateReservation, CompletedReservation, CashAdvance.
Possible values:

* **Award**
* **CashAdvance**
* **CompletedDeffered**
* **CompletedReservation**
* **Credit**
* **Debit**
* **Declined**
* **Failed**
* **FirstReservation**
* **IssuerInstalment**
* **OneTimeReservation**
* **Rebate**
* **Redemption**
* **ReverseAward**
* **ReverseCredit**
* **ReverseDebit**
* **ReverseRebate**
* **ReverseRedemption**
* **UpdateReservation**

## Enumeration

`TransactionType11Enum`

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
use AdyenLib\Models\TransactionType11Enum;

$transactionType11 = TransactionType11Enum::COMPLETEDRESERVATION;
```

