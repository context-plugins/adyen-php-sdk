
# Amount Min Max Requirement

## Structure

`AmountMinMaxRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies the eligible amounts for a particular route. | getDescription(): ?string | setDescription(?string description): void |
| `max` | `?int` | Optional | Maximum amount. | getMax(): ?int | setMax(?int max): void |
| `min` | `?int` | Optional | Minimum amount. | getMin(): ?int | setMin(?int min): void |
| `type` | `string` | Required, Constant | **amountMinMaxRequirement**<br><br>**Value**: `'amountMinMaxRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AmountMinMaxRequirementBuilder;

$amountMinMaxRequirement = AmountMinMaxRequirementBuilder::init()
    ->description('description6')
    ->max(18)
    ->min(156)
    ->build();
```

