
# Capital Grants

## Structure

`CapitalGrants`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `grants` | [`CapitalGrant[]`](../../doc/models/capital-grant.md) | Required | The unique identifier of the grant. | getGrants(): array | setGrants(array grants): void |

## Example

```php
use AdyenLib\Models\Builders\CapitalGrantsBuilder;
use AdyenLib\Models\Builders\CapitalGrantBuilder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Status14Enum;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\GrantCounterparty2Builder;
use AdyenLib\Models\Builders\Fee4Builder;
use AdyenLib\Models\Builders\RepaymentBuilder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;
use AdyenLib\Models\Builders\ThresholdRepayment2Builder;

$capitalGrants = CapitalGrantsBuilder::init(
    [
        CapitalGrantBuilder::init(
            CapitalBalanceBuilder::init(
                'currency0',
                72,
                110,
                150
            )->build(),
            'grantAccountId6',
            'grantOfferId6',
            'id0',
            Status14Enum::PENDING
        )
            ->amount(
                Amount17Builder::init(
                    'currency2',
                    110
                )->build()
            )
            ->counterparty(
                GrantCounterparty2Builder::init()
                    ->accountHolderId('accountHolderId0')
                    ->balanceAccountId('balanceAccountId0')
                    ->transferInstrumentId('transferInstrumentId4')
                    ->build()
            )
            ->fee(
                Fee4Builder::init(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )->build()
            )
            ->repayment(
                RepaymentBuilder::init(
                    18
                )
                    ->term(
                        RepaymentTermBuilder::init(
                            248
                        )
                            ->maximumDays(24)
                            ->build()
                    )
                    ->threshold(
                        ThresholdRepayment2Builder::init(
                            Amount17Builder::init(
                                'currency2',
                                110
                            )->build()
                        )->build()
                    )->build()
            )->build()
    ]
)->build();
```

