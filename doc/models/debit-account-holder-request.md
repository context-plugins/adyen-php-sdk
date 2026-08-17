
# Debit Account Holder Request

## Structure

`DebitAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount to be debited from the account holder's bank account. | getAmount(): Amount | setAmount(Amount amount): void |
| `bankAccountUUID` | `string` | Required | The Adyen-generated unique alphanumeric identifier (UUID) of the account holder's bank account. | getBankAccountUUID(): string | setBankAccountUUID(string bankAccountUUID): void |
| `description` | `?string` | Optional | A description of the direct debit. Maximum length: 35 characters.<br><br>Allowed characters: **a-z**, **A-Z**, **0-9**, and special characters **/?:().,'+ ";**.<br><br>**Constraints**: *Maximum Length*: `35` | getDescription(): ?string | setDescription(?string description): void |
| `merchantAccount` | `string` | Required | Your merchant account. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `splits` | [`Split1[]`](../../doc/models/split-1.md) | Required | Contains instructions on how to split the funds between the accounts in your platform. The request must have at least one split item. | getSplits(): array | setSplits(array splits): void |

## Example

```php
use AdyenLib\Models\Builders\DebitAccountHolderRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\Split1Builder;
use AdyenLib\Models\Type60Enum;
use AdyenLib\Models\Builders\SplitAmountBuilder;

$debitAccountHolderRequest = DebitAccountHolderRequestBuilder::init(
    'accountHolderCode8',
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'bankAccountUUID2',
    'merchantAccount2',
    [
        Split1Builder::init(
            Type60Enum::TIP
        )
            ->account('account2')
            ->amount(
                SplitAmountBuilder::init(
                    110
                )
                    ->currency('currency2')
                    ->build()
            )
            ->description('description2')
            ->reference('reference2')
            ->build()
    ]
)
    ->description('description4')
    ->build();
```

