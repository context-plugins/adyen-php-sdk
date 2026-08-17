
# Terminal Product Price 2

The price of the product.

## Structure

`TerminalProductPrice2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). | getCurrency(): ?string | setCurrency(?string currency): void |
| `value` | `?float` | Optional | The price of the item. | getValue(): ?float | setValue(?float value): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalProductPrice2Builder;

$terminalProductPrice2 = TerminalProductPrice2Builder::init()
    ->currency('currency6')
    ->value(57.26)
    ->build();
```

