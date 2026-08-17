
# Iban Account Identification Requirement

## Structure

`IbanAccountIdentificationRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies the allowed prefixes for the international bank account number as defined in the ISO-13616 standard. | getDescription(): ?string | setDescription(?string description): void |
| `ibanPrefixes` | `?(string[])` | Optional | Contains the list of allowed prefixes for international bank accounts. For example: NL, US, UK. | getIbanPrefixes(): ?array | setIbanPrefixes(?array ibanPrefixes): void |
| `type` | `string` | Required, Constant | **ibanAccountIdentificationRequirement**<br><br>**Value**: `'ibanAccountIdentificationRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\IbanAccountIdentificationRequirementBuilder;

$ibanAccountIdentificationRequirement = IbanAccountIdentificationRequirementBuilder::init()
    ->description('description4')
    ->ibanPrefixes(
        [
            'ibanPrefixes6',
            'ibanPrefixes7'
        ]
    )
    ->build();
```

