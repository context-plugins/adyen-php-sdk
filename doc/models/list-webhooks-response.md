
# List Webhooks Response

## Structure

`ListWebhooksResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `accountReference` | `?string` | Optional | Reference to the account. | getAccountReference(): ?string | setAccountReference(?string accountReference): void |
| `data` | [`?(Webhook[])`](../../doc/models/webhook.md) | Optional | The list of webhooks configured for this account. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListWebhooksResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\WebhookBuilder;
use AdyenLib\Models\CommunicationFormatEnum;
use AdyenLib\Models\Builders\WebhookLinks2Builder;
use AdyenLib\Models\Builders\LinksElement16Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElement19Builder;
use AdyenLib\Models\Builders\LinksElement15Builder;
use AdyenLib\Models\Builders\LinksElement17Builder;

$listWebhooksResponse = ListWebhooksResponseBuilder::init(
    144,
    106
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
    ->accountReference('accountReference0')
    ->data(
        [
            WebhookBuilder::init(
                false,
                CommunicationFormatEnum::JSON,
                'type0',
                'url4'
            )
                ->links(
                    WebhookLinks2Builder::init(
                        LinksElement16Builder::init()
                            ->href('href6')
                            ->build(),
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build(),
                        LinksElement19Builder::init()
                            ->href('href6')
                            ->build()
                    )
                        ->company(
                            LinksElement15Builder::init()
                                ->href('href2')
                                ->build()
                        )
                        ->merchant(
                            LinksElement17Builder::init()
                                ->href('href6')
                                ->build()
                        )
                        ->build()
                )
                ->acceptsExpiredCertificate(false)
                ->acceptsSelfSignedCertificate(false)
                ->acceptsUntrustedRootCertificate(false)
                ->accountReference('accountReference2')
                ->build(),
            WebhookBuilder::init(
                false,
                CommunicationFormatEnum::JSON,
                'type0',
                'url4'
            )
                ->links(
                    WebhookLinks2Builder::init(
                        LinksElement16Builder::init()
                            ->href('href6')
                            ->build(),
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build(),
                        LinksElement19Builder::init()
                            ->href('href6')
                            ->build()
                    )
                        ->company(
                            LinksElement15Builder::init()
                                ->href('href2')
                                ->build()
                        )
                        ->merchant(
                            LinksElement17Builder::init()
                                ->href('href6')
                                ->build()
                        )
                        ->build()
                )
                ->acceptsExpiredCertificate(false)
                ->acceptsSelfSignedCertificate(false)
                ->acceptsUntrustedRootCertificate(false)
                ->accountReference('accountReference2')
                ->build()
        ]
    )
    ->build();
```

