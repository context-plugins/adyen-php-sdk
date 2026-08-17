
# Token Requestors Restriction

## Structure

`TokenRequestorsRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\TokenRequestorsRestrictionBuilder;

$tokenRequestorsRestriction = TokenRequestorsRestrictionBuilder::init(
    'operation0'
)
    ->value(
        [
            'value4',
            'value5',
            'value6'
        ]
    )
    ->build();
```

