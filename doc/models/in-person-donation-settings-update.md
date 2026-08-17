
# In Person Donation Settings Update

## Structure

`InPersonDonationSettingsUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defaultAmount` | [DonationAmountUpdate](../../doc/models/donation-amount-update.md)\|null | Optional | This is a container for one-of cases. | getDefaultAmount(): ?DonationAmountUpdate | setDefaultAmount(?DonationAmountUpdate defaultAmount): void |
| `displayTextField` | [`?string(DisplayTextField2Enum)`](../../doc/models/display-text-field-2-enum.md) | Optional | The text shown on the payment terminal, either the name or the cause of the nonprofit organization. | getDisplayTextField(): ?string | setDisplayTextField(?string displayTextField): void |
| `donationFlow` | [`?string(DonationFlow1Enum)`](../../doc/models/donation-flow-1-enum.md) | Optional | The interaction flow for in-person donations. Possible values:<br><br>- **oneStep**: The shopper presents their payment method for the payment and the donation in one go, after the donation.<br><br>- **twoStep**: The shopper presents their payment method twice: after the payment and after the donation. | getDonationFlow(): ?string | setDonationFlow(?string donationFlow): void |
| `donationType` | string([DonationTypeEnum](../../doc/models/donation-type-enum.md))\|null | Optional | This is a container for one-of cases. | getDonationType(): ?string | setDonationType(?string donationType): void |
| `merchantAccounts` | `?(string[])` | Optional | The merchant accounts for this sales channel that are associated with the donation campaign. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |
| `presentCardTimeoutMs` | `?int` | Optional | Required if `donationFlow` is set to **twoStep**. The time, in milliseconds, that the terminal waits for the shopper to present their card. Defaults to **10000** (10 seconds). Range: 5000 to 15000. | getPresentCardTimeoutMs(): ?int | setPresentCardTimeoutMs(?int presentCardTimeoutMs): void |
| `promptTimeoutMs` | `?int` | Optional | The time, in milliseconds, that the terminal waits for the shopper to make a selection on the donation screen. Defaults to **10000** (10 seconds). Range: 5000 to 15000. | getPromptTimeoutMs(): ?int | setPromptTimeoutMs(?int promptTimeoutMs): void |
| `storeIds` | `?(string[])` | Optional | The Adyen-generated unique identifiers of stores for this sales channel that are associated with the donation campaign. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |

## Example

```php
use AdyenLib\Models\Builders\InPersonDonationSettingsUpdateBuilder;
use AdyenLib\Models\Builders\DonationAmountUpdateBuilder;
use AdyenLib\Models\DisplayTextField2Enum;
use AdyenLib\Models\DonationFlow1Enum;
use AdyenLib\Models\DonationTypeEnum;

$inPersonDonationSettingsUpdate = InPersonDonationSettingsUpdateBuilder::init()
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
            'merchantAccounts2'
        ]
    )
    ->build();
```

