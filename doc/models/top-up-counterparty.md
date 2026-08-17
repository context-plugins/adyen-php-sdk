
# Top Up Counterparty

## Structure

`TopUpCounterparty`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferInstrumentId` | `string` | Required | The unique identifier of the [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments#responses-200-id) that is funding the top-up. | getTransferInstrumentId(): string | setTransferInstrumentId(string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\TopUpCounterpartyBuilder;

$topUpCounterparty = TopUpCounterpartyBuilder::init(
    'transferInstrumentId2'
)->build();
```

