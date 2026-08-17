
# Terminal Models Response

## Structure

`TerminalModelsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(Item[])`](../../doc/models/item.md) | Optional | The terminal models that the API credential has access to. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalModelsResponseBuilder;
use AdyenLib\Models\Builders\ItemBuilder;

$terminalModelsResponse = TerminalModelsResponseBuilder::init()
    ->data(
        [
            ItemBuilder::init()
                ->id('id0')
                ->name('name0')
                ->build(),
            ItemBuilder::init()
                ->id('id0')
                ->name('name0')
                ->build(),
            ItemBuilder::init()
                ->id('id0')
                ->name('name0')
                ->build()
        ]
    )
    ->build();
```

