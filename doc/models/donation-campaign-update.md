
# Donation Campaign Update

## Structure

`DonationCampaignUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderIds` | `?(string[])` | Optional | The unique identifiers of the account holders associated with the donation campaign. | getAccountHolderIds(): ?array | setAccountHolderIds(?array accountHolderIds): void |
| `inPerson` | [InPersonDonationSettingsUpdate](../../doc/models/in-person-donation-settings-update.md)\|null | Optional | This is a container for one-of cases. | getInPerson(): ?InPersonDonationSettingsUpdate | setInPerson(?InPersonDonationSettingsUpdate inPerson): void |
| `name` | `?string` | Optional | The name of the donation campaign.<br><br>**Constraints**: *Minimum Length*: `1` | getName(): ?string | setName(?string name): void |
| `online` | [OnlineDonationSettingsUpdate](../../doc/models/online-donation-settings-update.md)\|null | Optional | This is a container for one-of cases. | getOnline(): ?OnlineDonationSettingsUpdate | setOnline(?OnlineDonationSettingsUpdate online): void |

## Example

```php
use AdyenLib\Models\Builders\DonationCampaignUpdateBuilder;
use AdyenLib\Models\Builders\InPersonDonationSettingsUpdateBuilder;
use AdyenLib\Models\Builders\DonationAmountUpdateBuilder;
use AdyenLib\Models\DisplayTextField2Enum;
use AdyenLib\Models\DonationFlow1Enum;
use AdyenLib\Models\DonationTypeEnum;
use AdyenLib\Models\Builders\OnlineDonationSettingsUpdateBuilder;

$donationCampaignUpdate = DonationCampaignUpdateBuilder::init()
    ->accountHolderIds(
        [
            'accountHolderIds9',
            'accountHolderIds0',
            'accountHolderIds1'
        ]
    )
    ->inPerson(
        InPersonDonationSettingsUpdateBuilder::init()
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
            ->displayTextField(DisplayTextField2Enum::CAUSENAME)
            ->donationFlow(DonationFlow1Enum::ONESTEP)
            ->donationType(
                DonationTypeEnum::FIXEDAMOUNTSROUNDUP
            )
            ->merchantAccounts(
                [
                    'merchantAccounts4'
                ]
            )
            ->build()
    )
    ->name('name4')
    ->online(
        OnlineDonationSettingsUpdateBuilder::init()
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
                DonationTypeEnum::ROUNDUP
            )
            ->merchantAccounts(
                [
                    'merchantAccounts6',
                    'merchantAccounts5',
                    'merchantAccounts4'
                ]
            )
            ->storeIds(
                [
                    'storeIds1',
                    'storeIds2',
                    'storeIds3'
                ]
            )
            ->build()
    )
    ->build();
```

