
# List Stores Response

## Structure

`ListStoresResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(Store[])`](../../doc/models/store.md) | Optional | List of stores | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListStoresResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\StoreBuilder;
use AdyenLib\Models\Builders\Links7Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\StoreLocation1Builder;

$listStoresResponse = ListStoresResponseBuilder::init(
    92,
    202
)
    ->links(
        PaginationLinks1Builder::init(
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
            ->build()
    )
    ->data(
        [
            StoreBuilder::init()
                ->links(
                    Links7Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->address(
                    StoreLocation1Builder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->line1('line18')
                        ->line2('line20')
                        ->line3('line38')
                        ->postalCode('postalCode8')
                        ->build()
                )
                ->businessLineIds(
                    [
                        'businessLineIds4'
                    ]
                )
                ->description('description0')
                ->externalReferenceId('externalReferenceId8')
                ->build(),
            StoreBuilder::init()
                ->links(
                    Links7Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->address(
                    StoreLocation1Builder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->line1('line18')
                        ->line2('line20')
                        ->line3('line38')
                        ->postalCode('postalCode8')
                        ->build()
                )
                ->businessLineIds(
                    [
                        'businessLineIds4'
                    ]
                )
                ->description('description0')
                ->externalReferenceId('externalReferenceId8')
                ->build()
        ]
    )
    ->build();
```

