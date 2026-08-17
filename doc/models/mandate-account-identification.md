
# Mandate Account Identification

## Structure

`MandateAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\MandateAccountIdentificationBuilder;

$mandateAccountIdentification = MandateAccountIdentificationBuilder::init()
    ->type('MandateAccountIdentification')
    ->build();
```

