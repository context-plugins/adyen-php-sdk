
# Terminal Product Price

## Structure

`TerminalProductPrice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). | getCurrency(): ?string | setCurrency(?string currency): void |
| `value` | `?float` | Optional | The price of the item. | getValue(): ?float | setValue(?float value): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalProductPriceBuilder;

$terminalProductPrice = TerminalProductPriceBuilder::init()
    ->currency('currency4')
    ->value(26.68)
    ->build();
```

