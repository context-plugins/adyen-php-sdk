
# US International Ach Address Requirement

## Structure

`USInternationalAchAddressRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies that you must provide a complete street address for International ACH (IAT) transactions. | getDescription(): ?string | setDescription(?string description): void |
| `type` | `string` | Required, Constant | **usInternationalAchAddressRequirement**<br><br>**Value**: `'usInternationalAchAddressRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\USInternationalAchAddressRequirementBuilder;

$uSInternationalAchAddressRequirement = USInternationalAchAddressRequirementBuilder::init()
    ->description('description2')
    ->build();
```

