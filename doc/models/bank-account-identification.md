
# Bank Account Identification

## Structure

`BankAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountIdentificationBuilder;

$bankAccountIdentification = BankAccountIdentificationBuilder::init()
    ->type('BankAccountIdentification')
    ->build();
```

