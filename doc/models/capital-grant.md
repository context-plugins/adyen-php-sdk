
# Capital Grant

## Structure

`CapitalGrant`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | An object containing the amount of the grant, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |
| `balances` | [`CapitalBalance`](../../doc/models/capital-balance.md) | Required | An object containing the details of the existing grant. | getBalances(): CapitalBalance | setBalances(CapitalBalance balances): void |
| `counterparty` | [`?GrantCounterparty2`](../../doc/models/grant-counterparty-2.md) | Optional | An object containing the details of the receiving party of the grant. | getCounterparty(): ?GrantCounterparty2 | setCounterparty(?GrantCounterparty2 counterparty): void |
| `fee` | [`?Fee4`](../../doc/models/fee-4.md) | Optional | An object containing the fee currency and value, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getFee(): ?Fee4 | setFee(?Fee4 fee): void |
| `grantAccountId` | `string` | Required | The identifier of the grant account used for the grant. | getGrantAccountId(): string | setGrantAccountId(string grantAccountId): void |
| `grantOfferId` | `string` | Required | The identifier of the grant offer that has been selected and from which the grant details will be used. | getGrantOfferId(): string | setGrantOfferId(string grantOfferId): void |
| `id` | `string` | Required | The identifier of the grant reference. | getId(): string | setId(string id): void |
| `repayment` | [`?Repayment`](../../doc/models/repayment.md) | Optional | An object containing the details of the 30-day repayment threshold. | getRepayment(): ?Repayment | setRepayment(?Repayment repayment): void |
| `status` | [`string(Status14Enum)`](../../doc/models/status-14-enum.md) | Required | The current status of the grant. Possible values: **Pending**, **Active**, **Repaid**, **WrittenOff**, **Failed**, **Revoked**. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\CapitalGrantBuilder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Status14Enum;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\GrantCounterparty2Builder;
use AdyenLib\Models\Builders\Fee4Builder;
use AdyenLib\Models\Builders\RepaymentBuilder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;
use AdyenLib\Models\Builders\ThresholdRepayment2Builder;

$capitalGrant = CapitalGrantBuilder::init(
    CapitalBalanceBuilder::init(
        'currency0',
        72,
        110,
        150
    )->build(),
    'grantAccountId8',
    'grantOfferId4',
    'id2',
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
    )->build();
```

