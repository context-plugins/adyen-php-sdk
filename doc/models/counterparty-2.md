
# Counterparty 2

## Structure

`Counterparty2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolder` | [`AccountHolder11`](../../doc/models/account-holder-11.md) | Required | Contains the full name of the person or entity that receives the payment funds). | getAccountHolder(): AccountHolder11 | setAccountHolder(AccountHolder11 accountHolder): void |
| `accountIdentification` | [`AccountIdentification1`](../../doc/models/account-identification-1.md) | Required | Contains the account number to which the payment funds are sent. | getAccountIdentification(): AccountIdentification1 | setAccountIdentification(AccountIdentification1 accountIdentification): void |

## Example

```php
use AdyenLib\Models\Builders\Counterparty2Builder;
use AdyenLib\Models\Builders\AccountHolder11Builder;
use AdyenLib\Models\Builders\AccountIdentification1Builder;

$counterparty2 = Counterparty2Builder::init(
    AccountHolder11Builder::init(
        'John Doe'
    )->build(),
    AccountIdentification1Builder::init()
        ->type('AccountIdentification1')
        ->build()
)->build();
```

