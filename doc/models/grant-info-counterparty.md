
# Grant Info Counterparty

Contains the details of the party that receives the grant.

## Structure

`GrantInfoCounterparty`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | The identifier of the balance account that belongs to the receiving account holder. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `transferInstrumentId` | `?string` | Optional | The identifier of the transfer instrument that belongs to the legal entity of the account holder. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\GrantInfoCounterpartyBuilder;

$grantInfoCounterparty = GrantInfoCounterpartyBuilder::init()
    ->balanceAccountId('balanceAccountId8')
    ->transferInstrumentId('transferInstrumentId4')
    ->build();
```

