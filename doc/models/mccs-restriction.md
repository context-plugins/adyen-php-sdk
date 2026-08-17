
# Mccs Restriction

## Structure

`MccsRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | List of merchant category codes (MCCs). | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MccsRestrictionBuilder;

$mccsRestriction = MccsRestrictionBuilder::init(
    'operation0'
)
    ->value(
        [
            'value4'
        ]
    )
    ->build();
```

