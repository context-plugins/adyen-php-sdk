
# Links 3

## Structure

`Links3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `next` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | Contains a link to the next page. | getNext(): ?LinksElement | setNext(?LinksElement next): void |
| `prev` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | Contains a link to the previous page. | getPrev(): ?LinksElement | setPrev(?LinksElement prev): void |

## Example

```php
use AdyenLib\Models\Builders\Links3Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;

$links3 = Links3Builder::init()
    ->next(
        LinksElementBuilder::init()
            ->href('href4')
            ->build()
    )
    ->prev(
        LinksElementBuilder::init()
            ->href('href8')
            ->build()
    )
    ->build();
```

