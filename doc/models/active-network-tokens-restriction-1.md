
# Active Network Tokens Restriction 1

The total number of tokens that a card can have across different kinds of digital wallets on the user's phones, watches, or other wearables.

Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**.

## Structure

`ActiveNetworkTokensRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | The number of tokens. | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\ActiveNetworkTokensRestriction1Builder;

$activeNetworkTokensRestriction1 = ActiveNetworkTokensRestriction1Builder::init(
    'operation0'
)
    ->value(224)
    ->build();
```

