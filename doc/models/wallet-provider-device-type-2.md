
# Wallet Provider Device Type 2

Wallet Provider Device Type and the operation.

Supported operations: **anyMatch**, **noneMatch**.

Supported value inputs:

- **MOBILE_PHONE**

- **TABLET_OR_EREADER**

- **WATCH_OR_WRISTBAND**

- **WEARABLE**

- **CARD**

- **PC**

- **OTHER**

- **UNKNOWN**

## Structure

`WalletProviderDeviceType2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value6Enum)[])`](../../doc/models/value-6-enum.md) | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\WalletProviderDeviceType2Builder;
use AdyenLib\Models\Value6Enum;

$walletProviderDeviceType2 = WalletProviderDeviceType2Builder::init(
    'operation4'
)
    ->value(
        [
            Value6Enum::WATCH_OR_WRISTBAND,
            Value6Enum::WEARABLE,
            Value6Enum::CARD
        ]
    )
    ->build();
```

