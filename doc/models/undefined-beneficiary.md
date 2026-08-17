
# Undefined Beneficiary

## Structure

`UndefinedBeneficiary`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The details of the undefined beneficiary. | getDescription(): ?string | setDescription(?string description): void |
| `reference` | `?string` | Optional, Read-only | The reference of the undefined beneficiary. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\UndefinedBeneficiaryBuilder;

$undefinedBeneficiary = UndefinedBeneficiaryBuilder::init()
    ->description('description6')
    ->build();
```

