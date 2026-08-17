
# Online Donation Settings Update

## Structure

`OnlineDonationSettingsUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defaultAmount` | [DonationAmountUpdate](../../doc/models/donation-amount-update.md)\|null | Optional | This is a container for one-of cases. | getDefaultAmount(): ?DonationAmountUpdate | setDefaultAmount(?DonationAmountUpdate defaultAmount): void |
| `donationType` | string([DonationTypeEnum](../../doc/models/donation-type-enum.md))\|null | Optional | This is a container for one-of cases. | getDonationType(): ?string | setDonationType(?string donationType): void |
| `merchantAccounts` | `?(string[])` | Optional | The merchant accounts for this sales channel that are associated with the donation campaign. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |
| `storeIds` | `?(string[])` | Optional | The Adyen-generated unique identifiers of stores for this sales channel that are associated with the donation campaign. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |

## Example

```php
use AdyenLib\Models\Builders\OnlineDonationSettingsUpdateBuilder;
use AdyenLib\Models\Builders\DonationAmountUpdateBuilder;
use AdyenLib\Models\DonationTypeEnum;

$onlineDonationSettingsUpdate = OnlineDonationSettingsUpdateBuilder::init()
    ->defaultAmount(
        DonationAmountUpdateBuilder::init()
            ->amounts(
                [
                    40
                ]
            )
            ->currencyCode('currencyCode2')
            ->build()
    )
    ->donationType(
        DonationTypeEnum::FIXEDAMOUNTSROUNDUP
    )
    ->merchantAccounts(
        [
            'merchantAccounts4'
        ]
    )
    ->storeIds(
        [
            'storeIds9',
            'storeIds0'
        ]
    )
    ->build();
```

