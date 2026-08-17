
# Direct Debit Au

## Structure

`DirectDebitAu`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccountNumber` | `?string` | Optional | The shopper's banking account number used to complete payment. | getBankAccountNumber(): ?string | setBankAccountNumber(?string bankAccountNumber): void |
| `bankBranchCode` | `?string` | Optional | The shopper's BSB (their bank's branch code) number used to complete payment. | getBankBranchCode(): ?string | setBankBranchCode(?string bankBranchCode): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `holderName` | `string` | Required | The name of the bank account holder. | getHolderName(): string | setHolderName(string holderName): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type22Enum)`](../../doc/models/type-22-enum.md) | Optional | **directdebit_AU**<br><br>**Default**: `Type22Enum::DIRECTDEBIT_AU` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\DirectDebitAuBuilder;
use AdyenLib\Models\Type22Enum;

$directDebitAu = DirectDebitAuBuilder::init(
    'holderName6'
)
    ->bankAccountNumber('bankAccountNumber0')
    ->bankBranchCode('bankBranchCode0')
    ->checkoutAttemptId('checkoutAttemptId6')
    ->recurringDetailReference('recurringDetailReference0')
    ->sdkData('sdkData0')
    ->type(Type22Enum::DIRECTDEBIT_AU)
    ->build();
```

