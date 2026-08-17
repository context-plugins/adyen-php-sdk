
# List Company Response

## Structure

`ListCompanyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(Company2[])`](../../doc/models/company-2.md) | Optional | The list of companies. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListCompanyResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\Company2Builder;
use AdyenLib\Models\Builders\CompanyLinks2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\DataCenterBuilder;

$listCompanyResponse = ListCompanyResponseBuilder::init(
    244,
    50
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
            Company2Builder::init()
                ->links(
                    CompanyLinks2Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )
                        ->apiCredentials(
                            LinksElementBuilder::init()
                                ->href('href8')
                                ->build()
                        )
                        ->users(
                            LinksElementBuilder::init()
                                ->href('href8')
                                ->build()
                        )
                        ->webhooks(
                            LinksElementBuilder::init()
                                ->href('href8')
                                ->build()
                        )
                        ->build()
                )
                ->dataCenters(
                    [
                        DataCenterBuilder::init()
                            ->livePrefix('livePrefix4')
                            ->name('name6')
                            ->build(),
                        DataCenterBuilder::init()
                            ->livePrefix('livePrefix4')
                            ->name('name6')
                            ->build(),
                        DataCenterBuilder::init()
                            ->livePrefix('livePrefix4')
                            ->name('name6')
                            ->build()
                    ]
                )
                ->description('description0')
                ->id('id0')
                ->name('name0')
                ->build(),
            Company2Builder::init()
                ->links(
                    CompanyLinks2Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )
                        ->apiCredentials(
                            LinksElementBuilder::init()
                                ->href('href8')
                                ->build()
                        )
                        ->users(
                            LinksElementBuilder::init()
                                ->href('href8')
                                ->build()
                        )
                        ->webhooks(
                            LinksElementBuilder::init()
                                ->href('href8')
                                ->build()
                        )
                        ->build()
                )
                ->dataCenters(
                    [
                        DataCenterBuilder::init()
                            ->livePrefix('livePrefix4')
                            ->name('name6')
                            ->build(),
                        DataCenterBuilder::init()
                            ->livePrefix('livePrefix4')
                            ->name('name6')
                            ->build(),
                        DataCenterBuilder::init()
                            ->livePrefix('livePrefix4')
                            ->name('name6')
                            ->build()
                    ]
                )
                ->description('description0')
                ->id('id0')
                ->name('name0')
                ->build()
        ]
    )
    ->build();
```

