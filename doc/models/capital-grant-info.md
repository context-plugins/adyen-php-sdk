
# Capital Grant Info

## Structure

`CapitalGrantInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `counterparty` | [`?GrantInfoCounterparty2`](../../doc/models/grant-info-counterparty-2.md) | Optional | An object containing the details of the receiving party of the grant. | getCounterparty(): ?GrantInfoCounterparty2 | setCounterparty(?GrantInfoCounterparty2 counterparty): void |
| `grantAccountId` | `string` | Required | The identifier of the grant account used for the grant. | getGrantAccountId(): string | setGrantAccountId(string grantAccountId): void |
| `grantOfferId` | `string` | Required | The identifier of the grant offer that has been selected and from which the grant details will be used. | getGrantOfferId(): string | setGrantOfferId(string grantOfferId): void |

## Example

```php
use AdyenLib\Models\Builders\CapitalGrantInfoBuilder;
use AdyenLib\Models\Builders\GrantInfoCounterparty2Builder;

$capitalGrantInfo = CapitalGrantInfoBuilder::init(
    'grantAccountId0',
    'grantOfferId2'
)
    ->counterparty(
        GrantInfoCounterparty2Builder::init()
            ->balanceAccountId('balanceAccountId0')
            ->transferInstrumentId('transferInstrumentId4')
            ->build()
    )
    ->build();
```

