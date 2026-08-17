
# Wallet Provider Account Score Restriction

## Structure

`WalletProviderAccountScoreRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | - | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\WalletProviderAccountScoreRestrictionBuilder;

$walletProviderAccountScoreRestriction = WalletProviderAccountScoreRestrictionBuilder::init(
    'operation0'
)
    ->value(108)
    ->build();
```

