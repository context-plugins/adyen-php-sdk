
# Terminal Product

## Structure

`TerminalProduct`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Information about items included and integration options. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the product. | getId(): ?string | setId(?string id): void |
| `itemsIncluded` | `?(string[])` | Optional | A list of parts included in the terminal package. | getItemsIncluded(): ?array | setItemsIncluded(?array itemsIncluded): void |
| `name` | `?string` | Optional | The descriptive name of the product. | getName(): ?string | setName(?string name): void |
| `price` | [`?TerminalProductPrice2`](../../doc/models/terminal-product-price-2.md) | Optional | The price of the product. | getPrice(): ?TerminalProductPrice2 | setPrice(?TerminalProductPrice2 price): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalProductBuilder;
use AdyenLib\Models\Builders\TerminalProductPrice2Builder;

$terminalProduct = TerminalProductBuilder::init()
    ->description('description0')
    ->id('id0')
    ->itemsIncluded(
        [
            'itemsIncluded3'
        ]
    )
    ->name('name0')
    ->price(
        TerminalProductPrice2Builder::init()
            ->currency('currency2')
            ->value(203.04)
            ->build()
    )
    ->build();
```

