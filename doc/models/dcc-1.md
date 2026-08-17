
# Dcc 1

Settings for Dynamic Currency Conversion (DCC).

## Structure

`Dcc1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enableDcc` | `?bool` | Optional | Enable Dynamic Currency Conversion (DCC). When you enable DCC, you are responsible for complying with [DCC receipt requirements and terms of use](https://help.adyen.com/en_US/knowledge/in-person-payments/terminal-features/dynamic-currency-conversion-dcc-rules-regulations). | getEnableDcc(): ?bool | setEnableDcc(?bool enableDcc): void |

## Example

```php
use AdyenLib\Models\Builders\Dcc1Builder;

$dcc1 = Dcc1Builder::init()
    ->enableDcc(false)
    ->build();
```

