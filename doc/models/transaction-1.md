
# Transaction 1

## Structure

`Transaction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount`](../../doc/models/amount.md) | Optional | The amount of the transaction. | getAmount(): ?Amount | setAmount(?Amount amount): void |
| `bankAccountDetail` | [`?BankAccountDetail`](../../doc/models/bank-account-detail.md) | Optional | The details of the bank account to where a payout was made. | getBankAccountDetail(): ?BankAccountDetail | setBankAccountDetail(?BankAccountDetail bankAccountDetail): void |
| `captureMerchantReference` | `?string` | Optional | The merchant reference of a related capture. | getCaptureMerchantReference(): ?string | setCaptureMerchantReference(?string captureMerchantReference): void |
| `capturePspReference` | `?string` | Optional | The psp reference of a related capture. | getCapturePspReference(): ?string | setCapturePspReference(?string capturePspReference): void |
| `creationDate` | `?DateTime` | Optional | The date on which the transaction was performed. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `description` | `?string` | Optional | A description of the transaction. | getDescription(): ?string | setDescription(?string description): void |
| `destinationAccountCode` | `?string` | Optional | The code of the account to which funds were credited during an outgoing fund transfer. | getDestinationAccountCode(): ?string | setDestinationAccountCode(?string destinationAccountCode): void |
| `disputePspReference` | `?string` | Optional | The psp reference of the related dispute. | getDisputePspReference(): ?string | setDisputePspReference(?string disputePspReference): void |
| `disputeReasonCode` | `?string` | Optional | The reason code of a dispute. | getDisputeReasonCode(): ?string | setDisputeReasonCode(?string disputeReasonCode): void |
| `merchantReference` | `?string` | Optional | The merchant reference of a transaction. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `paymentPspReference` | `?string` | Optional | The psp reference of the related authorisation or transfer. | getPaymentPspReference(): ?string | setPaymentPspReference(?string paymentPspReference): void |
| `payoutPspReference` | `?string` | Optional | The psp reference of the related payout. | getPayoutPspReference(): ?string | setPayoutPspReference(?string payoutPspReference): void |
| `pspReference` | `?string` | Optional | The psp reference of a transaction. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `sourceAccountCode` | `?string` | Optional | The code of the account from which funds were debited during an incoming fund transfer. | getSourceAccountCode(): ?string | setSourceAccountCode(?string sourceAccountCode): void |
| `transactionStatus` | [`?string(TransactionStatus1Enum)`](../../doc/models/transaction-status-1-enum.md) | Optional | The status of the transaction.<br><br>> Permitted values: `PendingCredit`, `CreditFailed`, `CreditClosed`, `CreditSuspended`, `Credited`, `Converted`, `PendingDebit`, `DebitFailed`, `Debited`, `DebitReversedReceived`, `DebitedReversed`, `ChargebackReceived`, `Chargeback`, `ChargebackReversedReceived`, `ChargebackReversed`, `Payout`, `PayoutReversed`, `FundTransfer`, `PendingFundTransfer`, `ManualCorrected`. | getTransactionStatus(): ?string | setTransactionStatus(?string transactionStatus): void |
| `transferCode` | `?string` | Optional | The transfer code of the transaction. | getTransferCode(): ?string | setTransferCode(?string transferCode): void |

## Example

```php
use AdyenLib\Models\Builders\Transaction1Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\BankAccountDetailBuilder;
use AdyenLib\Utils\DateTimeHelper;

$transaction1 = Transaction1Builder::init()
    ->amount(
        AmountBuilder::init(
            'currency2',
            110
        )->build()
    )
    ->bankAccountDetail(
        BankAccountDetailBuilder::init()
            ->accountNumber('accountNumber8')
            ->accountType('accountType4')
            ->bankAccountName('bankAccountName4')
            ->bankAccountReference('bankAccountReference4')
            ->bankAccountUUID('bankAccountUUID0')
            ->build()
    )
    ->captureMerchantReference('captureMerchantReference6')
    ->capturePspReference('capturePspReference4')
    ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

