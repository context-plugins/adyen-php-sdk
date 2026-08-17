
# US International Ach Priority Requirement

## Structure

`USInternationalAchPriorityRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies that transactions deemed to be International ACH (IAT) per OFAC/NACHA rules cannot have fast priority. | getDescription(): ?string | setDescription(?string description): void |
| `type` | `string` | Required, Constant | **usInternationalAchPriorityRequirement**<br><br>**Value**: `'usInternationalAchPriorityRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\USInternationalAchPriorityRequirementBuilder;

$uSInternationalAchPriorityRequirement = USInternationalAchPriorityRequirementBuilder::init()
    ->description('description0')
    ->build();
```

