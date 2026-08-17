
# Wallet Provider Account Score Restriction 2

Checks the wallet account score.

Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**.

## Structure

`WalletProviderAccountScoreRestriction2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | - | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\WalletProviderAccountScoreRestriction2Builder;

$walletProviderAccountScoreRestriction2 = WalletProviderAccountScoreRestriction2Builder::init(
    'operation2'
)
    ->value(154)
    ->build();
```

