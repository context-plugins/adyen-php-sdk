
# List Merchant Response

## Structure

`ListMerchantResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(Merchant[])`](../../doc/models/merchant.md) | Optional | The list of merchant accounts. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListMerchantResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\MerchantBuilder;
use AdyenLib\Models\Builders\MerchantLinks2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\DataCenterBuilder;

$listMerchantResponse = ListMerchantResponseBuilder::init(
    18,
    236
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
            MerchantBuilder::init()
                ->links(
                    MerchantLinks2Builder::init(
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
                ->captureDelay('captureDelay6')
                ->companyId('companyId0')
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
                ->defaultShopperInteraction('defaultShopperInteraction8')
                ->build(),
            MerchantBuilder::init()
                ->links(
                    MerchantLinks2Builder::init(
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
                ->captureDelay('captureDelay6')
                ->companyId('companyId0')
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
                ->defaultShopperInteraction('defaultShopperInteraction8')
                ->build(),
            MerchantBuilder::init()
                ->links(
                    MerchantLinks2Builder::init(
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
                ->captureDelay('captureDelay6')
                ->companyId('companyId0')
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
                ->defaultShopperInteraction('defaultShopperInteraction8')
                ->build()
        ]
    )
    ->build();
```

