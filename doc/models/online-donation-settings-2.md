
# Online Donation Settings 2

The settings for online donations collected as part of the campaign.

## Structure

`OnlineDonationSettings2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defaultAmount` | [`?DonationAmount1`](../../doc/models/donation-amount-1.md) | Optional | The default amount for donations. | getDefaultAmount(): ?DonationAmount1 | setDefaultAmount(?DonationAmount1 defaultAmount): void |
| `donationType` | [`?string(DonationType1Enum)`](../../doc/models/donation-type-1-enum.md) | Optional | The type of donation to collect from the shopper. Possible values:<br><br>- **roundup**: Round up the transaction amount.<br><br>- **fixedAmounts**: Choose a fixed amount.<br><br>- **fixedAmountsRoundup**: Round up, or choose a fixed amount. | getDonationType(): ?string | setDonationType(?string donationType): void |
| `merchantAccounts` | `?(string[])` | Optional | The merchant accounts for this sales channel that are associated with the donation campaign. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |
| `storeIds` | `?(string[])` | Optional | The Adyen-generated unique identifiers of stores for this sales channel that are associated with the donation campaign. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |

## Example

```php
use AdyenLib\Models\Builders\OnlineDonationSettings2Builder;
use AdyenLib\Models\Builders\DonationAmount1Builder;
use AdyenLib\Models\DonationType1Enum;

$onlineDonationSettings2 = OnlineDonationSettings2Builder::init()
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
    ->storeIds(
        [
            'storeIds9'
        ]
    )
    ->build();
```

