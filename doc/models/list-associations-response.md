
# List Associations Response

## Structure

`ListAssociationsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`Link3`](../../doc/models/link-3.md) | Required | A list of hyperlinks to resources related to this response. | getLinks(): Link3 | setLinks(Link3 links): void |
| `data` | [`AssociationListing[]`](../../doc/models/association-listing.md) | Required | Contains a list of associations and their corresponding details. | getData(): array | setData(array data): void |
| `itemsTotal` | `int` | Required | The total number of items available. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | The total number of pages available. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListAssociationsResponseBuilder;
use AdyenLib\Models\Builders\Link3Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\AssociationListingBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\ScaEntityType2Enum;
use AdyenLib\Models\ScaDeviceType3Enum;
use AdyenLib\Models\AssociationStatus1Enum;

$listAssociationsResponse = ListAssociationsResponseBuilder::init(
    Link3Builder::init()
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
        ->build(),
    [
        AssociationListingBuilder::init(
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
            'entityId8',
            ScaEntityType2Enum::LEGALENTITY,
            'BSDR11111111111A1AAA1AAAAA1AA1',
            ScaDeviceType3Enum::ANDROID,
            AssociationStatus1Enum::PENDINGAPPROVAL
        )
            ->scaDeviceName('scaDeviceName0')
            ->build()
    ],
    1,
    1
)->build();
```

