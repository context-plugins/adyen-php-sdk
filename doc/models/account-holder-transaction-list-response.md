
# Account Holder Transaction List Response

## Structure

`AccountHolderTransactionListResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountTransactionLists` | [`?(AccountTransactionList[])`](../../doc/models/account-transaction-list.md) | Optional | A list of the transactions. | getAccountTransactionLists(): ?array | setAccountTransactionLists(?array accountTransactionLists): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderTransactionListResponseBuilder;
use AdyenLib\Models\Builders\AccountTransactionListBuilder;
use AdyenLib\Models\Builders\Transaction1Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\BankAccountDetailBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$accountHolderTransactionListResponse = AccountHolderTransactionListResponseBuilder::init()
    ->accountTransactionLists(
        [
            AccountTransactionListBuilder::init()
                ->accountCode('accountCode8')
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
                ->build(),
            AccountTransactionListBuilder::init()
                ->accountCode('accountCode8')
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
                ->build(),
            AccountTransactionListBuilder::init()
                ->accountCode('accountCode8')
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
                ->build()
        ]
    )
    ->invalidFields(
        [
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build(),
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build(),
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build()
        ]
    )
    ->pspReference('pspReference8')
    ->resultCode('resultCode2')
    ->build();
```

