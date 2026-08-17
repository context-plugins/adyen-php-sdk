
# Donation Campaign Request

## Structure

`DonationCampaignRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderIds` | `?(string[])` | Optional | The unique identifiers of the account holders associated with the donation campaign. | getAccountHolderIds(): ?array | setAccountHolderIds(?array accountHolderIds): void |
| `inPerson` | [`?InPersonDonationSettings2`](../../doc/models/in-person-donation-settings-2.md) | Optional | The settings for in-person donations collected as part of the campaign. | getInPerson(): ?InPersonDonationSettings2 | setInPerson(?InPersonDonationSettings2 inPerson): void |
| `name` | `string` | Required | The name of the donation campaign.<br><br>**Constraints**: *Minimum Length*: `1` | getName(): string | setName(string name): void |
| `nonprofitCauseId` | `string` | Required | The unique identifier of the nonprofit cause that the campaign supports.<br><br>**Constraints**: *Minimum Length*: `1` | getNonprofitCauseId(): string | setNonprofitCauseId(string nonprofitCauseId): void |
| `online` | [`?OnlineDonationSettings2`](../../doc/models/online-donation-settings-2.md) | Optional | The settings for online donations collected as part of the campaign. | getOnline(): ?OnlineDonationSettings2 | setOnline(?OnlineDonationSettings2 online): void |

## Example

```php
use AdyenLib\Models\Builders\DonationCampaignRequestBuilder;
use AdyenLib\Models\Builders\InPersonDonationSettings2Builder;
use AdyenLib\Models\DisplayTextField2Enum;
use AdyenLib\Models\DonationFlow1Enum;
use AdyenLib\Models\Builders\DonationAmount1Builder;
use AdyenLib\Models\DonationType1Enum;
use AdyenLib\Models\Builders\OnlineDonationSettings2Builder;

$donationCampaignRequest = DonationCampaignRequestBuilder::init(
    'name6',
    'nonprofitCauseId0'
)
    ->accountHolderIds(
        [
            'accountHolderIds1'
        ]
    )
    ->inPerson(
        InPersonDonationSettings2Builder::init(
            DisplayTextField2Enum::CAUSENAME,
            DonationFlow1Enum::ONESTEP
        )
            ->defaultAmount(
                DonationAmount1Builder::init(
                    [
                        78,
                        79,
                        80
                    ],
                    'currencyCode6'
                )->build()
            )
            ->donationType(DonationType1Enum::FIXEDAMOUNTSROUNDUP)
            ->merchantAccounts(
                [
                    'merchantAccounts6',
                    'merchantAccounts5',
                    'merchantAccounts4'
                ]
            )
            ->presentCardTimeoutMs(102)
            ->promptTimeoutMs(66)
            ->build()
    )
    ->online(
        OnlineDonationSettings2Builder::init()
            ->defaultAmount(
                DonationAmount1Builder::init(
                    [
                        78,
                        79,
                        80
                    ],
                    'currencyCode6'
                )->build()
            )
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
    ->build();
```

