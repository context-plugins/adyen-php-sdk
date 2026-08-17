
# Pagination Links 1

Pagination references.

## Structure

`PaginationLinks1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `first` | [`LinksElement9`](../../doc/models/links-element-9.md) | Required | The first page. | getFirst(): LinksElement9 | setFirst(LinksElement9 first): void |
| `last` | [`LinksElement10`](../../doc/models/links-element-10.md) | Required | The last page. | getLast(): LinksElement10 | setLast(LinksElement10 last): void |
| `next` | [`?LinksElement11`](../../doc/models/links-element-11.md) | Optional | The next page. Only present if there is a next page. | getNext(): ?LinksElement11 | setNext(?LinksElement11 next): void |
| `prev` | [`?LinksElement12`](../../doc/models/links-element-12.md) | Optional | The previous page. Only present if there is a previous page. | getPrev(): ?LinksElement12 | setPrev(?LinksElement12 prev): void |
| `self` | [`LinksElement13`](../../doc/models/links-element-13.md) | Required | The current page. | getSelf(): LinksElement13 | setSelf(LinksElement13 self): void |

## Example

```php
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;

$paginationLinks1 = PaginationLinks1Builder::init(
    LinksElement9Builder::init()
        ->href('href2')
        ->build(),
    LinksElement10Builder::init()
        ->href('href2')
        ->build(),
    LinksElement13Builder::init()
        ->href('href0')
        ->build()
)
    ->next(
        LinksElement11Builder::init()
            ->href('href4')
            ->build()
    )
    ->prev(
        LinksElement12Builder::init()
            ->href('href8')
            ->build()
    )
    ->build();
```

