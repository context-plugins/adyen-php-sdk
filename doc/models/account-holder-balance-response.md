
# Account Holder Balance Response

## Structure

`AccountHolderBalanceResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balancePerAccount` | [`?(AccountDetailBalance[])`](../../doc/models/account-detail-balance.md) | Optional | A list of each account and their balances. | getBalancePerAccount(): ?array | setBalancePerAccount(?array balancePerAccount): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `totalBalance` | [`?DetailBalance1`](../../doc/models/detail-balance-1.md) | Optional | The total balance of the account holder. | getTotalBalance(): ?DetailBalance1 | setTotalBalance(?DetailBalance1 totalBalance): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderBalanceResponseBuilder;
use AdyenLib\Models\Builders\AccountDetailBalanceBuilder;
use AdyenLib\Models\Builders\DetailBalance3Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;
use AdyenLib\Models\Builders\DetailBalance1Builder;

$accountHolderBalanceResponse = AccountHolderBalanceResponseBuilder::init()
    ->balancePerAccount(
        [
            AccountDetailBalanceBuilder::init()
                ->accountCode('accountCode8')
                ->detailBalance(
                    DetailBalance3Builder::init()
                        ->balance(
                            [
                                AmountBuilder::init(
                                    'currency4',
                                    128
                                )->build(),
                                AmountBuilder::init(
                                    'currency4',
                                    128
                                )->build()
                            ]
                        )
                        ->onHoldBalance(
                            [
                                AmountBuilder::init(
                                    'currency8',
                                    72
                                )->build(),
                                AmountBuilder::init(
                                    'currency8',
                                    72
                                )->build(),
                                AmountBuilder::init(
                                    'currency8',
                                    72
                                )->build()
                            ]
                        )
                        ->pendingBalance(
                            [
                                AmountBuilder::init(
                                    'currency2',
                                    254
                                )->build()
                            ]
                        )->build()
                )->build()
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
                ->build()
        ]
    )
    ->pspReference('pspReference4')
    ->resultCode('resultCode2')
    ->totalBalance(
        DetailBalance1Builder::init()
            ->balance(
                [
                    AmountBuilder::init(
                        'currency4',
                        128
                    )->build()
                ]
            )
            ->onHoldBalance(
                [
                    AmountBuilder::init(
                        'currency8',
                        72
                    )->build(),
                    AmountBuilder::init(
                        'currency8',
                        72
                    )->build(),
                    AmountBuilder::init(
                        'currency8',
                        72
                    )->build()
                ]
            )
            ->pendingBalance(
                [
                    AmountBuilder::init(
                        'currency2',
                        254
                    )->build(),
                    AmountBuilder::init(
                        'currency2',
                        254
                    )->build()
                ]
            )->build()
    )->build();
```

