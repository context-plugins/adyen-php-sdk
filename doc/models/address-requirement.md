
# Address Requirement

## Structure

`AddressRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies the required address related fields for a particular route. | getDescription(): ?string | setDescription(?string description): void |
| `requiredAddressFields` | [`?(string(RequiredAddressFieldEnum)[])`](../../doc/models/required-address-field-enum.md) | Optional | List of address fields. | getRequiredAddressFields(): ?array | setRequiredAddressFields(?array requiredAddressFields): void |
| `type` | `string` | Required, Constant | **addressRequirement**<br><br>**Value**: `'addressRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AddressRequirementBuilder;
use AdyenLib\Models\RequiredAddressFieldEnum;

$addressRequirement = AddressRequirementBuilder::init()
    ->description('description2')
    ->requiredAddressFields(
        [
            RequiredAddressFieldEnum::COUNTRY,
            RequiredAddressFieldEnum::CITY,
            RequiredAddressFieldEnum::STATEORPROVINCE
        ]
    )
    ->build();
```

