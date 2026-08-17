
# Source Account Types Restriction

## Structure

`SourceAccountTypesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value5Enum)[])`](../../doc/models/value-5-enum.md) | Optional | The list of source account types to be evaluated. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\SourceAccountTypesRestrictionBuilder;
use AdyenLib\Models\Value5Enum;

$sourceAccountTypesRestriction = SourceAccountTypesRestrictionBuilder::init(
    'operation0'
)
    ->value(
        [
            Value5Enum::BALANCEACCOUNT
        ]
    )
    ->build();
```

