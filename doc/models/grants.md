
# Grants

## Structure

`Grants`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `grants` | [`Grant[]`](../../doc/models/grant.md) | Required | Contains a list of the grants that the account holder has received. | getGrants(): array | setGrants(array grants): void |

## Example

```php
use AdyenLib\Models\Builders\GrantsBuilder;
use AdyenLib\Models\Builders\GrantBuilder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Builders\Status25Builder;
use AdyenLib\Models\CodeEnum;
use AdyenLib\Models\Builders\Action1Builder;
use AdyenLib\Models\Builders\GrantCounterpartyBuilder;

$grants = GrantsBuilder::init(
    [
        GrantBuilder::init(
            CapitalBalanceBuilder::init(
                'currency0',
                72,
                110,
                150
            )->build(),
            'grantAccountId6',
            'grantOfferId6',
            'id0',
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
            ->build()
    ]
)->build();
```

