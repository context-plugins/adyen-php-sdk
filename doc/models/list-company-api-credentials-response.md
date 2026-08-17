
# List Company Api Credentials Response

## Structure

`ListCompanyApiCredentialsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(CompanyApiCredential[])`](../../doc/models/company-api-credential.md) | Optional | The list of API credentials. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListCompanyApiCredentialsResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\CompanyApiCredentialBuilder;
use AdyenLib\Models\Builders\ApiCredentialLinks2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElement1Builder;
use AdyenLib\Models\Builders\LinksElement2Builder;
use AdyenLib\Models\Builders\LinksElement3Builder;
use AdyenLib\Models\Builders\LinksElement4Builder;
use AdyenLib\Models\Builders\LinksElement5Builder;
use AdyenLib\Models\Builders\AllowedOriginBuilder;
use AdyenLib\Models\Builders\Links2Builder;

$listCompanyApiCredentialsResponse = ListCompanyApiCredentialsResponseBuilder::init(
    36,
    254
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
            CompanyApiCredentialBuilder::init(
                false,
                [
                    'allowedIpAddresses5'
                ],
                'clientKey6',
                'id0',
                [
                    'roles8'
                ],
                'username0'
            )
                ->links(
                    ApiCredentialLinks2Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )
                        ->allowedOrigins(
                            LinksElement1Builder::init()
                                ->href('href6')
                                ->build()
                        )
                        ->company(
                            LinksElement2Builder::init()
                                ->href('href2')
                                ->build()
                        )
                        ->generateApiKey(
                            LinksElement3Builder::init()
                                ->href('href6')
                                ->build()
                        )
                        ->generateClientKey(
                            LinksElement4Builder::init()
                                ->href('href4')
                                ->build()
                        )
                        ->merchant(
                            LinksElement5Builder::init()
                                ->href('href6')
                                ->build()
                        )
                        ->build()
                )
                ->allowedOrigins(
                    [
                        AllowedOriginBuilder::init(
                            'domain0'
                        )
                            ->links(
                                Links2Builder::init(
                                    LinksElement6Builder::init()
                                        ->href('href0')
                                        ->build()
                                )->build()
                            )
                            ->id('id4')
                            ->build()
                    ]
                )
                ->associatedMerchantAccounts(
                    [
                        'associatedMerchantAccounts0',
                        'associatedMerchantAccounts1',
                        'associatedMerchantAccounts2'
                    ]
                )
                ->description('description0')
                ->subjectDN('subjectDN0')
                ->build()
        ]
    )
    ->build();
```

