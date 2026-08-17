
# Wallet Provider Device Score

## Structure

`WalletProviderDeviceScore`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?int` | Optional | - | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\WalletProviderDeviceScoreBuilder;

$walletProviderDeviceScore = WalletProviderDeviceScoreBuilder::init(
    'operation8'
)
    ->value(96)
    ->build();
```

