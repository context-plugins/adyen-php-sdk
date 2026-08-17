
# Grant

## Structure

`Grant`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balances` | [`CapitalBalance`](../../doc/models/capital-balance.md) | Required | Contains information about the balances of the grant. | getBalances(): CapitalBalance | setBalances(CapitalBalance balances): void |
| `counterparty` | [`?GrantCounterparty`](../../doc/models/grant-counterparty.md) | Optional | Contains the details of the party that receives the grant. | getCounterparty(): ?GrantCounterparty | setCounterparty(?GrantCounterparty counterparty): void |
| `grantAccountId` | `string` | Required | The unique identifier of the grant account that tracks this grant. | getGrantAccountId(): string | setGrantAccountId(string grantAccountId): void |
| `grantOfferId` | `string` | Required | The unique identifier of the selected offer. Adyen uses the details of the selected offer to create a grant. | getGrantOfferId(): string | setGrantOfferId(string grantOfferId): void |
| `id` | `string` | Required | The unique identifier of the grant reference. | getId(): string | setId(string id): void |
| `status` | [`Status25`](../../doc/models/status-25.md) | Required | Contains the status of the grant. | getStatus(): Status25 | setStatus(Status25 status): void |

## Example

```php
use AdyenLib\Models\Builders\GrantBuilder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Builders\Status25Builder;
use AdyenLib\Models\CodeEnum;
use AdyenLib\Models\Builders\Action1Builder;
use AdyenLib\Models\Builders\GrantCounterpartyBuilder;

$grant = GrantBuilder::init(
    CapitalBalanceBuilder::init(
        'currency0',
        72,
        110,
        150
    )->build(),
    'grantAccountId8',
    'grantOfferId4',
    'id2',
    Status25Builder::init(
        CodeEnum::REJECTED
    )
        ->actions(
            [
                Action1Builder::init(
                    'actionCode6',
                    false
                )->build()
            ]
        )->build()
)
    ->counterparty(
        GrantCounterpartyBuilder::init()
            ->accountHolderId('accountHolderId0')
            ->balanceAccountId('balanceAccountId0')
            ->transferInstrumentId('transferInstrumentId4')
            ->build()
    )
    ->build();
```

