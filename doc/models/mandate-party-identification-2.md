
# Mandate Party Identification 2

Contains information about the owner of the counterparty bank account.

## Structure

`MandatePartyIdentification2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fullName` | `?string` | Optional | The full name of the entity that owns the bank account.<br><br>Supported characters: [a-z] [A-Z] [0-9] , . ; : - — / \ + & ! ? @ ( ) " ' and space. | getFullName(): ?string | setFullName(?string fullName): void |

## Example

```php
use AdyenLib\Models\Builders\MandatePartyIdentification2Builder;

$mandatePartyIdentification2 = MandatePartyIdentification2Builder::init()
    ->fullName('fullName2')
    ->build();
```

