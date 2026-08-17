
# Disbursements

## Structure

`Disbursements`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disbursements` | [`Disbursement[]`](../../doc/models/disbursement.md) | Required | Contains a list of all disbursements related to the specified grant. | getDisbursements(): array | setDisbursements(array disbursements): void |

## Example

```php
use AdyenLib\Models\Builders\DisbursementsBuilder;
use AdyenLib\Models\Builders\DisbursementBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Builders\Fee22Builder;
use AdyenLib\Models\Builders\DisbursementRepayment2Builder;
use AdyenLib\Models\Builders\FundsCollectionBuilder;
use AdyenLib\Models\Builders\BankAccountIdentification1Builder;
use AdyenLib\Models\FundsCollectionType2Enum;

$disbursements = DisbursementsBuilder::init(
    [
        DisbursementBuilder::init(
            'accountHolderId0',
            Amount17Builder::init(
                'currency2',
                110
            )->build(),
            'balanceAccountId0',
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
            'grantId6',
            'id8',
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
                        ->build(),
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
            ->build()
    ]
)->build();
```

