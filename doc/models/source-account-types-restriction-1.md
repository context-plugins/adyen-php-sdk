
# Source Account Types Restriction 1

Contains a list of source account types and how they must be evaluated.

Supported operations: **anyMatch**, **noneMatch**.

Supported value inputs:

- **balanceAccount**
- **businessAccount**.

## Structure

`SourceAccountTypesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value5Enum)[])`](../../doc/models/value-5-enum.md) | Optional | The list of source account types to be evaluated. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\SourceAccountTypesRestriction1Builder;
use AdyenLib\Models\Value5Enum;

$sourceAccountTypesRestriction1 = SourceAccountTypesRestriction1Builder::init(
    'operation6'
)
    ->value(
        [
            Value5Enum::BALANCEACCOUNT,
            Value5Enum::BUSINESSACCOUNT
        ]
    )
    ->build();
```

