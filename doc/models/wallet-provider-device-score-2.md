
# Wallet Provider Device Score 2

Wallet Provider Device Score and the operation.

Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**.

## Structure

`WalletProviderDeviceScore2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | - | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\WalletProviderDeviceScore2Builder;

$walletProviderDeviceScore2 = WalletProviderDeviceScore2Builder::init(
    'operation8'
)
    ->value(196)
    ->build();
```

