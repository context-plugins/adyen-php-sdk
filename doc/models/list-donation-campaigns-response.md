
# List Donation Campaigns Response

## Structure

`ListDonationCampaignsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `campaigns` | [`?(DonationCampaign1[])`](../../doc/models/donation-campaign-1.md) | Optional | The list of donation campaigns. | getCampaigns(): ?array | setCampaigns(?array campaigns): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListDonationCampaignsResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\DonationCampaign1Builder;
use AdyenLib\Models\Builders\DonationCampaignNonprofitCause2Builder;
use AdyenLib\Models\DonationCampaignStatus2Enum;
use AdyenLib\Models\Builders\InPersonDonationSettingsResponse2Builder;
use AdyenLib\Models\Builders\DonationAmountBuilder;
use AdyenLib\Models\DisplayTextField1Enum;
use AdyenLib\Models\DonationFlow4Enum;
use AdyenLib\Models\DonationType1Enum;
use AdyenLib\Models\Builders\OnlineDonationSettingsResponse2Builder;

$listDonationCampaignsResponse = ListDonationCampaignsResponseBuilder::init(
    66,
    28
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
    ->campaigns(
        [
            DonationCampaign1Builder::init(
                '',
                'name6',
                DonationCampaignNonprofitCause2Builder::init()
                    ->bannerUrl('bannerUrl4')
                    ->causeId('causeId0')
                    ->description('description4')
                    ->globalWebsiteUrl('globalWebsiteUrl6')
                    ->goals(
                        [
                            'goals9'
                        ]
                    )
                    ->build(),
                DonationCampaignStatus2Enum::ACTIVE
            )
                ->accountHolderIds(
                    [
                        'accountHolderIds1',
                        'accountHolderIds2',
                        'accountHolderIds3'
                    ]
                )
                ->inPerson(
                    InPersonDonationSettingsResponse2Builder::init()
                        ->amounts(
                            [
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build()
                            ]
                        )
                        ->defaultCurrency('defaultCurrency0')
                        ->displayTextField(DisplayTextField1Enum::CAUSENAME)
                        ->donationFlow(DonationFlow4Enum::ONESTEP)
                        ->donationType(DonationType1Enum::FIXEDAMOUNTSROUNDUP)
                        ->build()
                )
                ->online(
                    OnlineDonationSettingsResponse2Builder::init()
                        ->amounts(
                            [
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build(),
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build(),
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build()
                            ]
                        )
                        ->defaultCurrency('defaultCurrency0')
                        ->donationType(DonationType1Enum::FIXEDAMOUNTS)
                        ->merchantAccounts(
                            [
                                'merchantAccounts4',
                                'merchantAccounts3',
                                'merchantAccounts2'
                            ]
                        )
                        ->storeIds(
                            [
                                'storeIds9',
                                'storeIds0',
                                'storeIds1'
                            ]
                        )
                        ->build()
                )
                ->build(),
            DonationCampaign1Builder::init(
                '',
                'name6',
                DonationCampaignNonprofitCause2Builder::init()
                    ->bannerUrl('bannerUrl4')
                    ->causeId('causeId0')
                    ->description('description4')
                    ->globalWebsiteUrl('globalWebsiteUrl6')
                    ->goals(
                        [
                            'goals9'
                        ]
                    )
                    ->build(),
                DonationCampaignStatus2Enum::ACTIVE
            )
                ->accountHolderIds(
                    [
                        'accountHolderIds1',
                        'accountHolderIds2',
                        'accountHolderIds3'
                    ]
                )
                ->inPerson(
                    InPersonDonationSettingsResponse2Builder::init()
                        ->amounts(
                            [
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build()
                            ]
                        )
                        ->defaultCurrency('defaultCurrency0')
                        ->displayTextField(DisplayTextField1Enum::CAUSENAME)
                        ->donationFlow(DonationFlow4Enum::ONESTEP)
                        ->donationType(DonationType1Enum::FIXEDAMOUNTSROUNDUP)
                        ->build()
                )
                ->online(
                    OnlineDonationSettingsResponse2Builder::init()
                        ->amounts(
                            [
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build(),
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build(),
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build()
                            ]
                        )
                        ->defaultCurrency('defaultCurrency0')
                        ->donationType(DonationType1Enum::FIXEDAMOUNTS)
                        ->merchantAccounts(
                            [
                                'merchantAccounts4',
                                'merchantAccounts3',
                                'merchantAccounts2'
                            ]
                        )
                        ->storeIds(
                            [
                                'storeIds9',
                                'storeIds0',
                                'storeIds1'
                            ]
                        )
                        ->build()
                )
                ->build(),
            DonationCampaign1Builder::init(
                '',
                'name6',
                DonationCampaignNonprofitCause2Builder::init()
                    ->bannerUrl('bannerUrl4')
                    ->causeId('causeId0')
                    ->description('description4')
                    ->globalWebsiteUrl('globalWebsiteUrl6')
                    ->goals(
                        [
                            'goals9'
                        ]
                    )
                    ->build(),
                DonationCampaignStatus2Enum::ACTIVE
            )
                ->accountHolderIds(
                    [
                        'accountHolderIds1',
                        'accountHolderIds2',
                        'accountHolderIds3'
                    ]
                )
                ->inPerson(
                    InPersonDonationSettingsResponse2Builder::init()
                        ->amounts(
                            [
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build()
                            ]
                        )
                        ->defaultCurrency('defaultCurrency0')
                        ->displayTextField(DisplayTextField1Enum::CAUSENAME)
                        ->donationFlow(DonationFlow4Enum::ONESTEP)
                        ->donationType(DonationType1Enum::FIXEDAMOUNTSROUNDUP)
                        ->build()
                )
                ->online(
                    OnlineDonationSettingsResponse2Builder::init()
                        ->amounts(
                            [
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build(),
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build(),
                                DonationAmountBuilder::init(
                                    [
                                        48,
                                        49,
                                        50
                                    ],
                                    'currencyCode6'
                                )->build()
                            ]
                        )
                        ->defaultCurrency('defaultCurrency0')
                        ->donationType(DonationType1Enum::FIXEDAMOUNTS)
                        ->merchantAccounts(
                            [
                                'merchantAccounts4',
                                'merchantAccounts3',
                                'merchantAccounts2'
                            ]
                        )
                        ->storeIds(
                            [
                                'storeIds9',
                                'storeIds0',
                                'storeIds1'
                            ]
                        )
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

