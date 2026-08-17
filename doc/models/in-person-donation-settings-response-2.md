
# In Person Donation Settings Response 2

The settings for in-person donations collected as part of the campaign.

## Structure

`InPersonDonationSettingsResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amounts` | [`?(DonationAmount[])`](../../doc/models/donation-amount.md) | Optional | The currency and fixed amounts for donations. We automatically add calculated amounts in other currencies for participating stores that use a different currency than the default. | getAmounts(): ?array | setAmounts(?array amounts): void |
| `defaultCurrency` | `?string` | Optional | The currency that was used in the request to set fixed donation amounts. Format: three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes). | getDefaultCurrency(): ?string | setDefaultCurrency(?string defaultCurrency): void |
| `displayTextField` | [`?string(DisplayTextField1Enum)`](../../doc/models/display-text-field-1-enum.md) | Optional | The text shown on the payment terminal, asking the shopper for a donation. | getDisplayTextField(): ?string | setDisplayTextField(?string displayTextField): void |
| `donationFlow` | [`?string(DonationFlow4Enum)`](../../doc/models/donation-flow-4-enum.md) | Optional | The interaction flow for in-person donations: complete payment for the purchase and the donation in one go, or separately. | getDonationFlow(): ?string | setDonationFlow(?string donationFlow): void |
| `donationType` | [`?string(DonationType1Enum)`](../../doc/models/donation-type-1-enum.md) | Optional | The type of donation to collect from the shopper. Possible values:<br><br>- **roundup**: Round up the transaction amount.<br><br>- **fixedAmounts**: Choose a fixed amount.<br><br>- **fixedAmountsRoundup**: Round up, or choose a fixed amount. | getDonationType(): ?string | setDonationType(?string donationType): void |
| `merchantAccounts` | `?(string[])` | Optional | The merchant accounts for this sales channel that are associated with the donation campaign. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |
| `presentCardTimeoutMs` | `?int` | Optional | The time, in milliseconds, that the terminal waits for the shopper to present their card. | getPresentCardTimeoutMs(): ?int | setPresentCardTimeoutMs(?int presentCardTimeoutMs): void |
| `promptTimeoutMs` | `?int` | Optional | The time, in milliseconds, that the terminal waits for the shopper to respond to the text asking for a donation. | getPromptTimeoutMs(): ?int | setPromptTimeoutMs(?int promptTimeoutMs): void |
| `storeIds` | `?(string[])` | Optional | The Adyen-generated unique identifiers of stores for this sales channel that are associated with the donation campaign. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |

## Example

```php
use AdyenLib\Models\Builders\InPersonDonationSettingsResponse2Builder;
use AdyenLib\Models\Builders\DonationAmountBuilder;
use AdyenLib\Models\DisplayTextField1Enum;
use AdyenLib\Models\DonationFlow4Enum;
use AdyenLib\Models\DonationType1Enum;

$inPersonDonationSettingsResponse2 = InPersonDonationSettingsResponse2Builder::init()
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
            )->build()
        ]
    )
    ->defaultCurrency('defaultCurrency8')
    ->displayTextField(DisplayTextField1Enum::CAUSENAME)
    ->donationFlow(DonationFlow4Enum::ONESTEP)
    ->donationType(DonationType1Enum::ROUNDUP)
    ->build();
```

