
# Counterparty 1

The recipient of the funds transfer. A bank account or a transfer instrument.

## Structure

`Counterparty1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccount` | [`?BankAccount11`](../../doc/models/bank-account-11.md) | Optional | Contains information about the bank account. | getBankAccount(): ?BankAccount11 | setBankAccount(?BankAccount11 bankAccount): void |
| `transferInstrumentId` | `?string` | Optional | The unique identifier of the [transfer instrument](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments__resParam_id). | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\Counterparty1Builder;
use AdyenLib\Models\Builders\BankAccount11Builder;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;

$counterparty1 = Counterparty1Builder::init()
    ->bankAccount(
        BankAccount11Builder::init(
            AULocalAccountIdentificationBuilder::init(
                'accountNumber4',
                'bsbCode8'
            )->build()
        )->build()
    )
    ->transferInstrumentId('transferInstrumentId6')
    ->build();
```

