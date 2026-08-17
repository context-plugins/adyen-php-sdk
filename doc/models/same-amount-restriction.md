
# Same Amount Restriction

## Structure

`SameAmountRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | - | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\SameAmountRestrictionBuilder;

$sameAmountRestriction = SameAmountRestrictionBuilder::init(
    'operation4'
)
    ->value(false)
    ->build();
```

