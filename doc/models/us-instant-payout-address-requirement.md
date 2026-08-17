
# US Instant Payout Address Requirement

## Structure

`USInstantPayoutAddressRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies that you must provide complete street addresses for the party and counterParty for transactions greater than USD 3000. | getDescription(): ?string | setDescription(?string description): void |
| `type` | `string` | Required, Constant | **usInstantPayoutAddressRequirement**<br><br>**Value**: `'usInstantPayoutAddressRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\USInstantPayoutAddressRequirementBuilder;

$uSInstantPayoutAddressRequirement = USInstantPayoutAddressRequirementBuilder::init()
    ->description('description2')
    ->build();
```

