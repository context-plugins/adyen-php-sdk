
# Top Up Counterparty 1

The details about the counterparty that is funding the top-up.

## Structure

`TopUpCounterparty1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferInstrumentId` | `string` | Required | The unique identifier of the [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments#responses-200-id) that is funding the top-up. | getTransferInstrumentId(): string | setTransferInstrumentId(string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\TopUpCounterparty1Builder;

$topUpCounterparty1 = TopUpCounterparty1Builder::init(
    'transferInstrumentId4'
)->build();
```

