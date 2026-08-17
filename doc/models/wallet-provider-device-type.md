
# Wallet Provider Device Type

## Structure

`WalletProviderDeviceType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value6Enum)[])`](../../doc/models/value-6-enum.md) | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\WalletProviderDeviceTypeBuilder;
use AdyenLib\Models\Value6Enum;

$walletProviderDeviceType = WalletProviderDeviceTypeBuilder::init(
    'operation4'
)
    ->value(
        [
            Value6Enum::CARD,
            Value6Enum::MOBILE_PHONE
        ]
    )
    ->build();
```

