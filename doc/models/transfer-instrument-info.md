
# Transfer Instrument Info

## Structure

`TransferInstrumentInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccount` | [`BankAccountInfo1`](../../doc/models/bank-account-info-1.md) | Required | Contains information about the legal entity's bank account. | getBankAccount(): BankAccountInfo1 | setBankAccount(BankAccountInfo1 bankAccount): void |
| `legalEntityId` | `string` | Required | The unique identifier of the [legal entity](https://docs.adyen.com/api-explorer/legalentity/latest/post/legalEntities#responses-200-id) that owns the transfer instrument. | getLegalEntityId(): string | setLegalEntityId(string legalEntityId): void |
| `type` | [`string(Type221Enum)`](../../doc/models/type-221-enum.md) | Required | The type of transfer instrument.<br><br>Possible value: **bankAccount**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\TransferInstrumentInfoBuilder;
use AdyenLib\Models\Builders\BankAccountInfo1Builder;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;
use AdyenLib\Models\Type221Enum;

$transferInstrumentInfo = TransferInstrumentInfoBuilder::init(
    BankAccountInfo1Builder::init()
        ->accountIdentification(
            AULocalAccountIdentificationBuilder::init(
                'accountNumber4',
                'bsbCode8'
            )->build()
        )
        ->accountType('accountType8')
        ->bankName('bankName6')
        ->countryCode('countryCode6')
        ->build(),
    'legalEntityId6',
    Type221Enum::BANKACCOUNT
)->build();
```

