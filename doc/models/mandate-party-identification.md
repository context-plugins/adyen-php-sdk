
# Mandate Party Identification

## Structure

`MandatePartyIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fullName` | `?string` | Optional | The full name of the entity that owns the bank account.<br><br>Supported characters: [a-z] [A-Z] [0-9] , . ; : - — / \ + & ! ? @ ( ) " ' and space. | getFullName(): ?string | setFullName(?string fullName): void |

## Example

```php
use AdyenLib\Models\Builders\MandatePartyIdentificationBuilder;

$mandatePartyIdentification = MandatePartyIdentificationBuilder::init()
    ->fullName('fullName0')
    ->build();
```

