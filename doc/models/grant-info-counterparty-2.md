
# Grant Info Counterparty 2

An object containing the details of the receiving party of the grant.

## Structure

`GrantInfoCounterparty2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | The identifier of the balance account that belongs to the receiving account holder. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `transferInstrumentId` | `?string` | Optional | The identifier of the transfer instrument that belongs to the legal entity of the account holder. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\GrantInfoCounterparty2Builder;

$grantInfoCounterparty2 = GrantInfoCounterparty2Builder::init()
    ->balanceAccountId('balanceAccountId8')
    ->transferInstrumentId('transferInstrumentId2')
    ->build();
```

