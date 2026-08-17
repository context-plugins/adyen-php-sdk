
# List Nonprofits Response

## Structure

`ListNonprofitsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `nonprofits` | [`?(Nonprofit[])`](../../doc/models/nonprofit.md) | Optional | The supported nonprofit organizations. | getNonprofits(): ?array | setNonprofits(?array nonprofits): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListNonprofitsResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\NonprofitBuilder;
use AdyenLib\Models\Builders\NonprofitCauseBuilder;

$listNonprofitsResponse = ListNonprofitsResponseBuilder::init(
    180,
    142
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
    ->nonprofits(
        [
            NonprofitBuilder::init(
                [
                    NonprofitCauseBuilder::init(
                        'bannerUrl6',
                        'description6',
                        [
                            'locales6',
                            'locales7'
                        ],
                        'name6'
                    )
                        ->id('id6')
                        ->build()
                ],
                'description8',
                [
                    'goals3',
                    'goals4',
                    'goals5'
                ],
                [
                    'locales8',
                    'locales9'
                ],
                'logoUrl8',
                'name8',
                [
                    'regions3',
                    'regions4'
                ],
                'termsAndConditionsUrl6',
                'website4'
            )
                ->id('id8')
                ->build()
        ]
    )
    ->build();
```

