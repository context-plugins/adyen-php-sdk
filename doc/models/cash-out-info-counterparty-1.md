
# Cash Out Info Counterparty 1

Contains information about the counterparty of the cashout transfer.

## Structure

`CashOutInfoCounterparty1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferInstrumentId` | `?string` | Optional | The unique identifier of the counterparty transfer instrument.<br><br>If you do not provide this field, the cashout funds remain in the instructing balance account after the cashout transfer is settled. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\CashOutInfoCounterparty1Builder;

$cashOutInfoCounterparty1 = CashOutInfoCounterparty1Builder::init()
    ->transferInstrumentId('transferInstrumentId8')
    ->build();
```

