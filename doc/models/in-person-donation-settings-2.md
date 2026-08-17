
# In Person Donation Settings 2

The settings for in-person donations collected as part of the campaign.

## Structure

`InPersonDonationSettings2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defaultAmount` | [`?DonationAmount1`](../../doc/models/donation-amount-1.md) | Optional | The default amount for donations. | getDefaultAmount(): ?DonationAmount1 | setDefaultAmount(?DonationAmount1 defaultAmount): void |
| `displayTextField` | [`string(DisplayTextField2Enum)`](../../doc/models/display-text-field-2-enum.md) | Required | The text shown on the payment terminal, either the name or the cause of the nonprofit organization. | getDisplayTextField(): string | setDisplayTextField(string displayTextField): void |
| `donationFlow` | [`string(DonationFlow1Enum)`](../../doc/models/donation-flow-1-enum.md) | Required | The interaction flow for in-person donations. Possible values:<br><br>- **oneStep**: The shopper presents their payment method for the payment and the donation in one go, after the donation.<br><br>- **twoStep**: The shopper presents their payment method twice: after the payment and after the donation. | getDonationFlow(): string | setDonationFlow(string donationFlow): void |
| `donationType` | [`?string(DonationType1Enum)`](../../doc/models/donation-type-1-enum.md) | Optional | The type of donation to collect from the shopper. Possible values:<br><br>- **roundup**: Round up the transaction amount.<br><br>- **fixedAmounts**: Choose a fixed amount.<br><br>- **fixedAmountsRoundup**: Round up, or choose a fixed amount. | getDonationType(): ?string | setDonationType(?string donationType): void |
| `merchantAccounts` | `?(string[])` | Optional | The merchant accounts for this sales channel that are associated with the donation campaign. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |
| `presentCardTimeoutMs` | `?int` | Optional | Required if `donationFlow` is set to **twoStep**. The time, in milliseconds, that the terminal waits for the shopper to present their card. Defaults to **10000** (10 seconds). Range: 5000 to 15000. | getPresentCardTimeoutMs(): ?int | setPresentCardTimeoutMs(?int presentCardTimeoutMs): void |
| `promptTimeoutMs` | `?int` | Optional | The time, in milliseconds, that the terminal waits for the shopper to make a selection on the donation screen. Defaults to **10000** (10 seconds). Range: 5000 to 15000. | getPromptTimeoutMs(): ?int | setPromptTimeoutMs(?int promptTimeoutMs): void |
| `storeIds` | `?(string[])` | Optional | The Adyen-generated unique identifiers of stores for this sales channel that are associated with the donation campaign. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |

## Example

```php
use AdyenLib\Models\Builders\InPersonDonationSettings2Builder;
use AdyenLib\Models\DisplayTextField2Enum;
use AdyenLib\Models\DonationFlow1Enum;
use AdyenLib\Models\Builders\DonationAmount1Builder;
use AdyenLib\Models\DonationType1Enum;

$inPersonDonationSettings2 = InPersonDonationSettings2Builder::init(
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
    ->donationType(DonationType1Enum::ROUNDUP)
    ->merchantAccounts(
        [
            'merchantAccounts2'
        ]
    )
    ->presentCardTimeoutMs(68)
    ->promptTimeoutMs(32)
    ->build();
```

