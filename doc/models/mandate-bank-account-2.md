
# Mandate Bank Account 2

Contains information to identify the counterparty.

## Structure

`MandateBankAccount2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolder` | [`MandatePartyIdentification2`](../../doc/models/mandate-party-identification-2.md) | Required | Contains information about the owner of the counterparty bank account. | getAccountHolder(): MandatePartyIdentification2 | setAccountHolder(MandatePartyIdentification2 accountHolder): void |
| `accountIdentification` | [`MandateAccountIdentification2`](../../doc/models/mandate-account-identification-2.md) | Required | Contains the bank account details of the counterparty. The fields required in this object depend on the country of the bank account and the currency of the transfer. | getAccountIdentification(): MandateAccountIdentification2 | setAccountIdentification(MandateAccountIdentification2 accountIdentification): void |

## Example

```php
use AdyenLib\Models\Builders\MandateBankAccount2Builder;
use AdyenLib\Models\Builders\MandatePartyIdentification2Builder;
use AdyenLib\Models\Builders\MandateAccountIdentification2Builder;

$mandateBankAccount2 = MandateBankAccount2Builder::init(
    MandatePartyIdentification2Builder::init()
        ->fullName('fullName0')
        ->build(),
    MandateAccountIdentification2Builder::init()
        ->type('MandateAccountIdentification2')
        ->build()
)->build();
```

