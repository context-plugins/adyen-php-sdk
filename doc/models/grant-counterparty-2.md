
# Grant Counterparty 2

An object containing the details of the receiving party of the grant.

## Structure

`GrantCounterparty2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `?string` | Optional | The identifier of the receiving account holder. | getAccountHolderId(): ?string | setAccountHolderId(?string accountHolderId): void |
| `balanceAccountId` | `?string` | Optional | The identifier of the balance account that belongs to the receiving account holder. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `transferInstrumentId` | `?string` | Optional | The identifier of the transfer instrument that belongs to the legal entity of the account holder. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\GrantCounterparty2Builder;

$grantCounterparty2 = GrantCounterparty2Builder::init()
    ->accountHolderId('accountHolderId8')
    ->balanceAccountId('balanceAccountId8')
    ->transferInstrumentId('transferInstrumentId4')
    ->build();
```

