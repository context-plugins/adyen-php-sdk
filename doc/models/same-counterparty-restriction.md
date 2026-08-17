
# Same Counterparty Restriction

## Structure

`SameCounterpartyRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | - | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\SameCounterpartyRestrictionBuilder;

$sameCounterpartyRestriction = SameCounterpartyRestrictionBuilder::init(
    'operation6'
)
    ->value(false)
    ->build();
```

