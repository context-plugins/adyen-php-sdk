
# Online Donation Settings Response 2

The settings for online donations collected as part of the campaign.

## Structure

`OnlineDonationSettingsResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amounts` | [`?(DonationAmount[])`](../../doc/models/donation-amount.md) | Optional | The currency and fixed amounts for donations. We automatically add calculated amounts in other currencies for participating stores that use a different currency than the default. | getAmounts(): ?array | setAmounts(?array amounts): void |
| `defaultCurrency` | `?string` | Optional | The currency that was used in the request to set fixed donation amounts. Format: three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes). | getDefaultCurrency(): ?string | setDefaultCurrency(?string defaultCurrency): void |
| `donationType` | [`?string(DonationType1Enum)`](../../doc/models/donation-type-1-enum.md) | Optional | The type of donation to collect from the shopper. Possible values:<br><br>- **roundup**: Round up the transaction amount.<br><br>- **fixedAmounts**: Choose a fixed amount.<br><br>- **fixedAmountsRoundup**: Round up, or choose a fixed amount. | getDonationType(): ?string | setDonationType(?string donationType): void |
| `merchantAccounts` | `?(string[])` | Optional | The merchant accounts for this sales channel that are associated with the donation campaign. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |
| `storeIds` | `?(string[])` | Optional | The Adyen-generated unique identifiers of stores for this sales channel that are associated with the donation campaign. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |

## Example

```php
use AdyenLib\Models\Builders\OnlineDonationSettingsResponse2Builder;
use AdyenLib\Models\Builders\DonationAmountBuilder;
use AdyenLib\Models\DonationType1Enum;

$onlineDonationSettingsResponse2 = OnlineDonationSettingsResponse2Builder::init()
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
    ->defaultCurrency('defaultCurrency4')
    ->donationType(DonationType1Enum::FIXEDAMOUNTS)
    ->merchantAccounts(
        [
            'merchantAccounts0',
            'merchantAccounts1',
            'merchantAccounts2'
        ]
    )
    ->storeIds(
        [
            'storeIds5',
            'storeIds6'
        ]
    )
    ->build();
```

