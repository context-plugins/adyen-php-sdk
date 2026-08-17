
# Dcc

## Structure

`Dcc`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enableDcc` | `?bool` | Optional | Enable Dynamic Currency Conversion (DCC). When you enable DCC, you are responsible for complying with [DCC receipt requirements and terms of use](https://help.adyen.com/en_US/knowledge/in-person-payments/terminal-features/dynamic-currency-conversion-dcc-rules-regulations). | getEnableDcc(): ?bool | setEnableDcc(?bool enableDcc): void |

## Example

```php
use AdyenLib\Models\Builders\DccBuilder;

$dcc = DccBuilder::init()
    ->enableDcc(false)
    ->build();
```

