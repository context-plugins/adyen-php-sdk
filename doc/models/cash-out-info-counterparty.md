
# Cash Out Info Counterparty

## Structure

`CashOutInfoCounterparty`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferInstrumentId` | `?string` | Optional | The unique identifier of the counterparty transfer instrument.<br><br>If you do not provide this field, the cashout funds remain in the instructing balance account after the cashout transfer is settled. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\CashOutInfoCounterpartyBuilder;

$cashOutInfoCounterparty = CashOutInfoCounterpartyBuilder::init()
    ->transferInstrumentId('transferInstrumentId6')
    ->build();
```

