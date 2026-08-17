
# Token Requestors Restriction 1

List of token requestor IDs and the operation.

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`TokenRequestorsRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\TokenRequestorsRestriction1Builder;

$tokenRequestorsRestriction1 = TokenRequestorsRestriction1Builder::init(
    'operation0'
)
    ->value(
        [
            'value4'
        ]
    )
    ->build();
```

