
# Show Pages 2

Contains indicators whether specific pages must be shown to the account holder.

## Structure

`ShowPages2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankDetailsSummaryPage` | `?bool` | Optional | Indicates whether the page with bank account details must be shown. Defaults to **true**. | getBankDetailsSummaryPage(): ?bool | setBankDetailsSummaryPage(?bool bankDetailsSummaryPage): void |
| `bankVerificationPage` | `?bool` | Optional | Indicates whether the bank check instant verification' details must be shown. Defaults to **true**. | getBankVerificationPage(): ?bool | setBankVerificationPage(?bool bankVerificationPage): void |
| `businessDetailsSummaryPage` | `?bool` | Optional | Indicates whether the page with the company's or organization's details must be shown. Defaults to **true**. | getBusinessDetailsSummaryPage(): ?bool | setBusinessDetailsSummaryPage(?bool businessDetailsSummaryPage): void |
| `checksOverviewPage` | `?bool` | Optional | Indicates whether the checks overview page must be shown. Defaults to **false**. | getChecksOverviewPage(): ?bool | setChecksOverviewPage(?bool checksOverviewPage): void |
| `individualDetailsSummaryPage` | `?bool` | Optional | Indicates whether the page with the individual's details must be shown. Defaults to **true**. | getIndividualDetailsSummaryPage(): ?bool | setIndividualDetailsSummaryPage(?bool individualDetailsSummaryPage): void |
| `legalArrangementsDetailsSummaryPage` | `?bool` | Optional | Indicates whether the page with the legal arrangements' details must be shown. Defaults to **true**. | getLegalArrangementsDetailsSummaryPage(): ?bool | setLegalArrangementsDetailsSummaryPage(?bool legalArrangementsDetailsSummaryPage): void |
| `manualBankAccountPage` | `?bool` | Optional | Indicates whether the page to manually add bank account' details must be shown. Defaults to **true**. | getManualBankAccountPage(): ?bool | setManualBankAccountPage(?bool manualBankAccountPage): void |
| `shareholderDetailsSummaryPage` | `?bool` | Optional | Indicates whether the page with the shareholders' details must be shown. Defaults to **true**. | getShareholderDetailsSummaryPage(): ?bool | setShareholderDetailsSummaryPage(?bool shareholderDetailsSummaryPage): void |
| `welcomePage` | `?bool` | Optional | Indicates whether the welcome page must be shown. Defaults to **false**. | getWelcomePage(): ?bool | setWelcomePage(?bool welcomePage): void |

## Example

```php
use AdyenLib\Models\Builders\ShowPages2Builder;

$showPages2 = ShowPages2Builder::init()
    ->bankDetailsSummaryPage(false)
    ->bankVerificationPage(false)
    ->businessDetailsSummaryPage(false)
    ->checksOverviewPage(false)
    ->individualDetailsSummaryPage(false)
    ->build();
```

