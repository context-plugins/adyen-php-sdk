
# Collect Information

## Structure

`CollectInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankDetails` | `?bool` | Optional | Indicates whether [bank account details](https://docs.adyen.com/classic-platforms/verification-process/accepted-data-format/#bank-accounts) must be collected. Default is **true**. | getBankDetails(): ?bool | setBankDetails(?bool bankDetails): void |
| `businessDetails` | `?bool` | Optional | Indicates whether [business details](https://docs.adyen.com/classic-platforms/verification-process/accepted-data-format/#organizations) must be collected. Default is **true**. | getBusinessDetails(): ?bool | setBusinessDetails(?bool businessDetails): void |
| `individualDetails` | `?bool` | Optional | Indicates whether [individual details](https://docs.adyen.com/classic-platforms/verification-process/accepted-data-format/#individuals) must be collected. Default is **true**. | getIndividualDetails(): ?bool | setIndividualDetails(?bool individualDetails): void |
| `legalArrangementDetails` | `?bool` | Optional | Indicates whether [legal arrangement details](https://docs.adyen.com/classic-platforms/verification-checks/legal-arrangements) must be collected. Default is **true**. | getLegalArrangementDetails(): ?bool | setLegalArrangementDetails(?bool legalArrangementDetails): void |
| `pciQuestionnaire` | `?bool` | Optional | Indicates whether answers to a [PCI questionnaire](https://docs.adyen.com/classic-platforms/platforms-for-partners#onboard-partner-platform) must be collected. Applies only to partner platforms. Default is **true**. | getPciQuestionnaire(): ?bool | setPciQuestionnaire(?bool pciQuestionnaire): void |
| `shareholderDetails` | `?bool` | Optional | Indicates whether [shareholder details](https://docs.adyen.com/classic-platforms/verification-process/accepted-data-format/#individuals) must be collected. Defaults to **true**. | getShareholderDetails(): ?bool | setShareholderDetails(?bool shareholderDetails): void |

## Example

```php
use AdyenLib\Models\Builders\CollectInformationBuilder;

$collectInformation = CollectInformationBuilder::init()
    ->bankDetails(false)
    ->businessDetails(false)
    ->individualDetails(false)
    ->legalArrangementDetails(false)
    ->pciQuestionnaire(false)
    ->build();
```

