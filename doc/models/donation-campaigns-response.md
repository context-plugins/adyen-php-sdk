
# Donation Campaigns Response

## Structure

`DonationCampaignsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `donationCampaigns` | [`?(DonationCampaign[])`](../../doc/models/donation-campaign.md) | Optional | List of active donation campaigns for your merchant account. | getDonationCampaigns(): ?array | setDonationCampaigns(?array donationCampaigns): void |

## Example

```php
use AdyenLib\Models\Builders\DonationCampaignsResponseBuilder;
use AdyenLib\Models\Builders\DonationCampaignBuilder;
use AdyenLib\Models\Builders\Amounts1Builder;
use AdyenLib\Models\Builders\Donation1Builder;

$donationCampaignsResponse = DonationCampaignsResponseBuilder::init()
    ->donationCampaigns(
        [
            DonationCampaignBuilder::init()
                ->amounts(
                    Amounts1Builder::init(
                        'currency6',
                        [
                            48,
                            49
                        ]
                    )->build()
                )
                ->bannerUrl('bannerUrl0')
                ->campaignName('campaignName2')
                ->causeName('causeName6')
                ->donation(
                    Donation1Builder::init(
                        'currency0',
                        'type0'
                    )
                        ->donationType('donationType2')
                        ->maxRoundupAmount(114)
                        ->values(
                            [
                                106,
                                105,
                                104
                            ]
                        )
                        ->build()
                )
                ->build(),
            DonationCampaignBuilder::init()
                ->amounts(
                    Amounts1Builder::init(
                        'currency6',
                        [
                            48,
                            49
                        ]
                    )->build()
                )
                ->bannerUrl('bannerUrl0')
                ->campaignName('campaignName2')
                ->causeName('causeName6')
                ->donation(
                    Donation1Builder::init(
                        'currency0',
                        'type0'
                    )
                        ->donationType('donationType2')
                        ->maxRoundupAmount(114)
                        ->values(
                            [
                                106,
                                105,
                                104
                            ]
                        )
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

