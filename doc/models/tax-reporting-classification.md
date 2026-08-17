
# Tax Reporting Classification

## Structure

`TaxReportingClassification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `businessType` | [`?string(BusinessTypeEnum)`](../../doc/models/business-type-enum.md) | Optional | The organization's business type.<br><br>Possible values: **other**, **listedPublicCompany**, **subsidiaryOfListedPublicCompany**, **governmentalOrganization**, **internationalOrganization**, **financialInstitution**. | getBusinessType(): ?string | setBusinessType(?string businessType): void |
| `financialInstitutionNumber` | `?string` | Optional | The Global Intermediary Identification Number (GIIN) required for FATCA. Only required if the organization is a US financial institution and the `businessType` is **financialInstitution**. | getFinancialInstitutionNumber(): ?string | setFinancialInstitutionNumber(?string financialInstitutionNumber): void |
| `mainSourceOfIncome` | [`?string(MainSourceOfIncomeEnum)`](../../doc/models/main-source-of-income-enum.md) | Optional | The organization's main source of income. Only required if `businessType` is **other**.<br><br>Possible values: **businessOperation**, **realEstateSales**, **investmentInterestOrRoyalty**, **propertyRental**, **other**. | getMainSourceOfIncome(): ?string | setMainSourceOfIncome(?string mainSourceOfIncome): void |
| `type` | [`?string(Type151Enum)`](../../doc/models/type-151-enum.md) | Optional | The tax reporting classification type.<br><br>Possible values: **nonFinancialNonReportable**, **financialNonReportable**, **nonFinancialActive**, **nonFinancialPassive**. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\TaxReportingClassificationBuilder;
use AdyenLib\Models\BusinessTypeEnum;
use AdyenLib\Models\MainSourceOfIncomeEnum;
use AdyenLib\Models\Type151Enum;

$taxReportingClassification = TaxReportingClassificationBuilder::init()
    ->businessType(BusinessTypeEnum::SUBSIDIARYOFLISTEDPUBLICCOMPANY)
    ->financialInstitutionNumber('financialInstitutionNumber2')
    ->mainSourceOfIncome(MainSourceOfIncomeEnum::PROPERTYRENTAL)
    ->type(Type151Enum::NONFINANCIALNONREPORTABLE)
    ->build();
```

