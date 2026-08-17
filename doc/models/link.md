
# Link

## Structure

`Link`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `first` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | The link to the first page of the list. | getFirst(): ?LinksElement | setFirst(?LinksElement first): void |
| `last` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | The link to the last page of the list. | getLast(): ?LinksElement | setLast(?LinksElement last): void |
| `next` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | The link to the next page of the list. | getNext(): ?LinksElement | setNext(?LinksElement next): void |
| `previous` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | The link to the previous page of the list. | getPrevious(): ?LinksElement | setPrevious(?LinksElement previous): void |
| `self` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | The link to the list page you are currently viewing. | getSelf(): ?LinksElement | setSelf(?LinksElement self): void |

## Example

```php
use AdyenLib\Models\Builders\LinkBuilder;
use AdyenLib\Models\Builders\LinksElementBuilder;

$link = LinkBuilder::init()
    ->first(
        LinksElementBuilder::init()
            ->href('href2')
            ->build()
    )
    ->last(
        LinksElementBuilder::init()
            ->href('href2')
            ->build()
    )
    ->next(
        LinksElementBuilder::init()
            ->href('href4')
            ->build()
    )
    ->previous(
        LinksElementBuilder::init()
            ->href('href0')
            ->build()
    )
    ->self(
        LinksElementBuilder::init()
            ->href('href0')
            ->build()
    )
    ->build();
```

