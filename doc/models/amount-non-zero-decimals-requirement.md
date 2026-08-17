
# Amount Non Zero Decimals Requirement

## Structure

`AmountNonZeroDecimalsRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies for which routes the amount in a transfer request must have no non-zero decimal places, so the transfer can only be processed if the amount consists of round numbers. | getDescription(): ?string | setDescription(?string description): void |
| `type` | `string` | Required, Constant | **amountNonZeroDecimalsRequirement**<br><br>**Value**: `'amountNonZeroDecimalsRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AmountNonZeroDecimalsRequirementBuilder;

$amountNonZeroDecimalsRequirement = AmountNonZeroDecimalsRequirementBuilder::init()
    ->description('description4')
    ->build();
```

