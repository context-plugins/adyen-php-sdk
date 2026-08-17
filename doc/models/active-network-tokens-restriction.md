
# Active Network Tokens Restriction

## Structure

`ActiveNetworkTokensRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | The number of tokens. | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\ActiveNetworkTokensRestrictionBuilder;

$activeNetworkTokensRestriction = ActiveNetworkTokensRestrictionBuilder::init(
    'operation8'
)
    ->value(140)
    ->build();
```

