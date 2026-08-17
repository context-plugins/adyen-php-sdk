
# Mccs Restriction 1

List of merchant category codes (MCCs) and the operation.

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`MccsRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | List of merchant category codes (MCCs). | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MccsRestriction1Builder;

$mccsRestriction1 = MccsRestriction1Builder::init(
    'operation8'
)
    ->value(
        [
            'value2'
        ]
    )
    ->build();
```

