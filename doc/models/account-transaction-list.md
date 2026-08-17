
# Account Transaction List

## Structure

`AccountTransactionList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `?string` | Optional | The code of the account. | getAccountCode(): ?string | setAccountCode(?string accountCode): void |
| `hasNextPage` | `?bool` | Optional | Indicates whether there is a next page of transactions available. | getHasNextPage(): ?bool | setHasNextPage(?bool hasNextPage): void |
| `transactions` | [`?(Transaction1[])`](../../doc/models/transaction-1.md) | Optional | The list of transactions. | getTransactions(): ?array | setTransactions(?array transactions): void |

## Example

```php
use AdyenLib\Models\Builders\AccountTransactionListBuilder;
use AdyenLib\Models\Builders\Transaction1Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\BankAccountDetailBuilder;
use AdyenLib\Utils\DateTimeHelper;

$accountTransactionList = AccountTransactionListBuilder::init()
    ->accountCode('accountCode0')
    ->hasNextPage(false)
    ->transactions(
        [
            Transaction1Builder::init()
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
                ->captureMerchantReference('captureMerchantReference8')
                ->capturePspReference('capturePspReference6')
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->build(),
            Transaction1Builder::init()
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
                ->captureMerchantReference('captureMerchantReference8')
                ->capturePspReference('capturePspReference6')
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->build()
        ]
    )
    ->build();
```

