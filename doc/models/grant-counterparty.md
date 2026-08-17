
# Grant Counterparty

Contains the details of the party that receives the grant.

## Structure

`GrantCounterparty`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `?string` | Optional | The identifier of the receiving account holder. | getAccountHolderId(): ?string | setAccountHolderId(?string accountHolderId): void |
| `balanceAccountId` | `?string` | Optional | The identifier of the balance account that belongs to the receiving account holder. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `transferInstrumentId` | `?string` | Optional | The identifier of the transfer instrument that belongs to the legal entity of the account holder. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\GrantCounterpartyBuilder;

$grantCounterparty = GrantCounterpartyBuilder::init()
    ->accountHolderId('accountHolderId2')
    ->balanceAccountId('balanceAccountId2')
    ->transferInstrumentId('transferInstrumentId6')
    ->build();
```

