
# Mandate Account Identification 2

Contains the bank account details of the counterparty. The fields required in this object depend on the country of the bank account and the currency of the transfer.

## Structure

`MandateAccountIdentification2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\MandateAccountIdentification2Builder;

$mandateAccountIdentification2 = MandateAccountIdentification2Builder::init()
    ->type('MandateAccountIdentification2')
    ->build();
```

