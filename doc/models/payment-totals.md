
# Payment Totals

Totals of the payment transaction during the reconciliation period.

## Structure

`PaymentTotals`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionType` | [`string(TransactionType11Enum)`](../../doc/models/transaction-type-11-enum.md) | Required | Type of transaction for which totals are grouped.<br>Debit, Credit, ReverseDebit, ReverseCredit, OneTimeReservation, CompletedDeffered, FirstReservation, UpdateReservation, CompletedReservation, CashAdvance.<br>Possible values:<br><br>* **Award**<br>* **CashAdvance**<br>* **CompletedDeffered**<br>* **CompletedReservation**<br>* **Credit**<br>* **Debit**<br>* **Declined**<br>* **Failed**<br>* **FirstReservation**<br>* **IssuerInstalment**<br>* **OneTimeReservation**<br>* **Rebate**<br>* **Redemption**<br>* **ReverseAward**<br>* **ReverseCredit**<br>* **ReverseDebit**<br>* **ReverseRebate**<br>* **ReverseRedemption**<br>* **UpdateReservation** | getTransactionType(): string | setTransactionType(string transactionType): void |
| `transactionCount` | `int` | Required | Number of processed transaction during the period. | getTransactionCount(): int | setTransactionCount(int transactionCount): void |
| `transactionAmount` | `float` | Required | Sum of amount of processed transaction during the period.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getTransactionAmount(): float | setTransactionAmount(float transactionAmount): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentTotalsBuilder;
use AdyenLib\Models\TransactionType11Enum;

$paymentTotals = PaymentTotalsBuilder::init(
    TransactionType11Enum::DECLINED,
    128,
    228.16
)->build();
```

