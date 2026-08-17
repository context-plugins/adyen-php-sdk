
# Counterparty Types Restriction

## Structure

`CounterpartyTypesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(ValueEnum)[])`](../../doc/models/value-enum.md) | Optional | The list of counterparty types to be evaluated. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\CounterpartyTypesRestrictionBuilder;
use AdyenLib\Models\ValueEnum;

$counterpartyTypesRestriction = CounterpartyTypesRestrictionBuilder::init(
    'operation4'
)
    ->value(
        [
            ValueEnum::CARD
        ]
    )
    ->build();
```

