
# Counterparty Types Restriction 1

Contains a list of counterparty types and how they must be evaluated.

Supported operations: **anyMatch**, **noneMatch**.

Supported value inputs:

- **balanceAccount**
- **bankAccount**
- **card**
- **transferInstrument**

## Structure

`CounterpartyTypesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(ValueEnum)[])`](../../doc/models/value-enum.md) | Optional | The list of counterparty types to be evaluated. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\CounterpartyTypesRestriction1Builder;
use AdyenLib\Models\ValueEnum;

$counterpartyTypesRestriction1 = CounterpartyTypesRestriction1Builder::init(
    'operation4'
)
    ->value(
        [
            ValueEnum::CARD
        ]
    )
    ->build();
```

