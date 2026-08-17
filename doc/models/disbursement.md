
# Disbursement

## Structure

`Disbursement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the account holder that received the disbursement. | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains information about the amount of the disbursement. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `balanceAccountId` | `string` | Required | The unique identifier of the balance account that received the disbursement. | getBalanceAccountId(): string | setBalanceAccountId(string balanceAccountId): void |
| `balances` | [`CapitalBalance`](../../doc/models/capital-balance.md) | Required | Contains information about the balances of the disbursement. | getBalances(): CapitalBalance | setBalances(CapitalBalance balances): void |
| `fee` | [`Fee22`](../../doc/models/fee-22.md) | Required | Contains information about the fee that your user must pay for the disbursement. | getFee(): Fee22 | setFee(Fee22 fee): void |
| `fundsCollections` | [`?(FundsCollection[])`](../../doc/models/funds-collection.md) | Optional | Contains information about the accounts that Adyen uses to collect funds related to repayments. | getFundsCollections(): ?array | setFundsCollections(?array fundsCollections): void |
| `grantId` | `string` | Required | The unique identifier of the grant related to the disbursement. | getGrantId(): string | setGrantId(string grantId): void |
| `id` | `string` | Required | The unique identifier of the disbursement. | getId(): string | setId(string id): void |
| `repayment` | [`DisbursementRepayment2`](../../doc/models/disbursement-repayment-2.md) | Required | Contains information about the basis points configured for repaying the disbursement. | getRepayment(): DisbursementRepayment2 | setRepayment(DisbursementRepayment2 repayment): void |

## Example

```php
use AdyenLib\Models\Builders\DisbursementBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Builders\Fee22Builder;
use AdyenLib\Models\Builders\DisbursementRepayment2Builder;
use AdyenLib\Models\Builders\FundsCollectionBuilder;
use AdyenLib\Models\Builders\BankAccountIdentification1Builder;
use AdyenLib\Models\FundsCollectionType2Enum;

$disbursement = DisbursementBuilder::init(
    'accountHolderId2',
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    'balanceAccountId2',
    CapitalBalanceBuilder::init(
        'currency0',
        72,
        110,
        150
    )->build(),
    Fee22Builder::init(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )->build(),
    'grantId8',
    'id0',
    DisbursementRepayment2Builder::init(
        18,
        'updateDescription0'
    )->build()
)
    ->fundsCollections(
        [
            FundsCollectionBuilder::init()
                ->accountIdentification(
                    BankAccountIdentification1Builder::init()
                        ->type('BankAccountIdentification1')
                        ->build()
                )
                ->fundsCollectionType(FundsCollectionType2Enum::UNSCHEDULEDREPAYMENT)
                ->build()
        ]
    )
    ->build();
```

