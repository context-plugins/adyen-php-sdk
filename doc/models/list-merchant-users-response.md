
# List Merchant Users Response

## Structure

`ListMerchantUsersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(User[])`](../../doc/models/user.md) | Optional | The list of users. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListMerchantUsersResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\UserBuilder;
use AdyenLib\Models\Builders\Links1Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\NameBuilder;

$listMerchantUsersResponse = ListMerchantUsersResponseBuilder::init(
    96,
    58
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
            UserBuilder::init(
                'email6',
                'id0',
                [
                    'roles8'
                ],
                'timeZoneCode2',
                'username0'
            )
                ->links(
                    Links1Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->accountGroups(
                    [
                        'accountGroups7'
                    ]
                )
                ->active(false)
                ->apps(
                    [
                        'apps4',
                        'apps5',
                        'apps6'
                    ]
                )
                ->name(
                    NameBuilder::init(
                        'firstName4',
                        'lastName4'
                    )->build()
                )->build(),
            UserBuilder::init(
                'email6',
                'id0',
                [
                    'roles8'
                ],
                'timeZoneCode2',
                'username0'
            )
                ->links(
                    Links1Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->accountGroups(
                    [
                        'accountGroups7'
                    ]
                )
                ->active(false)
                ->apps(
                    [
                        'apps4',
                        'apps5',
                        'apps6'
                    ]
                )
                ->name(
                    NameBuilder::init(
                        'firstName4',
                        'lastName4'
                    )->build()
                )->build()
        ]
    )->build();
```

