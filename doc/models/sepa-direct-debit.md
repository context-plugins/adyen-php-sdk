
# SEPA Direct Debit

## Structure

`SEPADirectDebit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `dueDate` | `?string` | Optional | The date that the the shopper's bank account is charged. | getDueDate(): ?string | setDueDate(?string dueDate): void |
| `iban` | `string` | Required | The International Bank Account Number (IBAN). | getIban(): string | setIban(string iban): void |
| `ownerName` | `string` | Required | The name of the bank account holder. | getOwnerName(): string | setOwnerName(string ownerName): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `transferInstrumentId` | `?string` | Optional | The unique identifier of your user's verified transfer instrument, which you can use to top up their balance accounts. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |
| `type` | [`?string(Type51Enum)`](../../doc/models/type-51-enum.md) | Optional | **sepadirectdebit**<br><br>**Default**: `Type51Enum::SEPADIRECTDEBIT` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\SEPADirectDebitBuilder;
use AdyenLib\Models\Type51Enum;

$sEPADirectDebit = SEPADirectDebitBuilder::init(
    'iban6',
    'ownerName6'
)
    ->checkoutAttemptId('checkoutAttemptId8')
    ->dueDate('dueDate8')
    ->recurringDetailReference('recurringDetailReference2')
    ->sdkData('sdkData8')
    ->storedPaymentMethodId('storedPaymentMethodId6')
    ->type(Type51Enum::SEPADIRECTDEBIT)
    ->build();
```

