
# Terminal Products Response

## Structure

`TerminalProductsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(TerminalProduct[])`](../../doc/models/terminal-product.md) | Optional | Terminal products that can be ordered. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalProductsResponseBuilder;
use AdyenLib\Models\Builders\TerminalProductBuilder;
use AdyenLib\Models\Builders\TerminalProductPrice2Builder;

$terminalProductsResponse = TerminalProductsResponseBuilder::init()
    ->data(
        [
            TerminalProductBuilder::init()
                ->description('description0')
                ->id('id0')
                ->itemsIncluded(
                    [
                        'itemsIncluded3',
                        'itemsIncluded4',
                        'itemsIncluded5'
                    ]
                )
                ->name('name0')
                ->price(
                    TerminalProductPrice2Builder::init()
                        ->currency('currency2')
                        ->value(203.04)
                        ->build()
                )
                ->build(),
            TerminalProductBuilder::init()
                ->description('description0')
                ->id('id0')
                ->itemsIncluded(
                    [
                        'itemsIncluded3',
                        'itemsIncluded4',
                        'itemsIncluded5'
                    ]
                )
                ->name('name0')
                ->price(
                    TerminalProductPrice2Builder::init()
                        ->currency('currency2')
                        ->value(203.04)
                        ->build()
                )
                ->build(),
            TerminalProductBuilder::init()
                ->description('description0')
                ->id('id0')
                ->itemsIncluded(
                    [
                        'itemsIncluded3',
                        'itemsIncluded4',
                        'itemsIncluded5'
                    ]
                )
                ->name('name0')
                ->price(
                    TerminalProductPrice2Builder::init()
                        ->currency('currency2')
                        ->value(203.04)
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

