
# Organization

## Structure

`Organization`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `countryOfGoverningLaw` | `?string` | Optional | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the governing country. | getCountryOfGoverningLaw(): ?string | setCountryOfGoverningLaw(?string countryOfGoverningLaw): void |
| `dateOfIncorporation` | `?string` | Optional | The date when the organization was incorporated in YYYY-MM-DD format. | getDateOfIncorporation(): ?string | setDateOfIncorporation(?string dateOfIncorporation): void |
| `dateOfInitiationOfLegalProceeding` | `?string` | Optional | Required if the value of `statusOfLegalProceeding` is one of the following:<br><br>**underJudicialAdministration**, **bankruptcyInsolvency**, **otherLegalMeasures**<br><br>The date at which a legal proceeding was initiated, in **YYYY-MM-DD** format. Example: **2000-02-12** | getDateOfInitiationOfLegalProceeding(): ?string | setDateOfInitiationOfLegalProceeding(?string dateOfInitiationOfLegalProceeding): void |
| `description` | `?string` | Optional | Your description for the organization. | getDescription(): ?string | setDescription(?string description): void |
| `doingBusinessAs` | `?string` | Optional | The organization's trading name, if different from the registered legal name. | getDoingBusinessAs(): ?string | setDoingBusinessAs(?string doingBusinessAs): void |
| `doingBusinessAsAbsent` | `?bool` | Optional | Set this to **true** if the organization or legal arrangement does not have a `Doing business as` name. | getDoingBusinessAsAbsent(): ?bool | setDoingBusinessAsAbsent(?bool doingBusinessAsAbsent): void |
| `economicSector` | `?string` | Optional | The sector of the economy the legal entity operates within, represented by a 2-4 digit code that may include a ".". Example: 45.11<br><br>You can locate economic sector codes for your area by referencing codes defined by the NACE (Nomenclature of Economic Activities) used in the European Union. | getEconomicSector(): ?string | setEconomicSector(?string economicSector): void |
| `email` | `?string` | Optional | The email address of the legal entity. | getEmail(): ?string | setEmail(?string email): void |
| `financialReports` | [`?(FinancialReport[])`](../../doc/models/financial-report.md) | Optional | The financial report information of the organization. | getFinancialReports(): ?array | setFinancialReports(?array financialReports): void |
| `globalLegalEntityIdentifier` | `?string` | Optional | The global legal entity identifier for the organization.<br><br>This field is not required if the `registrationNumber` for the organization has been provided. | getGlobalLegalEntityIdentifier(): ?string | setGlobalLegalEntityIdentifier(?string globalLegalEntityIdentifier): void |
| `headOfficeIndicator` | `?bool` | Optional | Indicates that the registered business address is also the company's headquarters. | getHeadOfficeIndicator(): ?bool | setHeadOfficeIndicator(?bool headOfficeIndicator): void |
| `institutionalSector` | [`?string(InstitutionalSectorEnum)`](../../doc/models/institutional-sector-enum.md) | Optional | The institutional sector the organization operates within. | getInstitutionalSector(): ?string | setInstitutionalSector(?string institutionalSector): void |
| `legalForm` | `?string` | Optional | The type of business entity as defined in the national legal system. Use a legal form listed within the accepted legal forms compiled by the Central Bank of Europe. | getLegalForm(): ?string | setLegalForm(?string legalForm): void |
| `legalName` | `string` | Required | The organization's legal name. | getLegalName(): string | setLegalName(string legalName): void |
| `phone` | [`?PhoneNumber2`](../../doc/models/phone-number-2.md) | Optional | The phone number of the legal entity. | getPhone(): ?PhoneNumber2 | setPhone(?PhoneNumber2 phone): void |
| `principalPlaceOfBusiness` | [`?Address22`](../../doc/models/address-22.md) | Optional | The address where the organization operates from. Provide this if the principal place of business is different from the `registeredAddress`. | getPrincipalPlaceOfBusiness(): ?Address22 | setPrincipalPlaceOfBusiness(?Address22 principalPlaceOfBusiness): void |
| `registeredAddress` | [`Address31`](../../doc/models/address-31.md) | Required | The address of the organization registered at their registrar (such as the Chamber of Commerce). | getRegisteredAddress(): Address31 | setRegisteredAddress(Address31 registeredAddress): void |
| `registrationNumber` | `?string` | Optional | The organization's registration number. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `registrationNumberAbsent` | `?bool` | Optional | Set this to **true** if the organization does not have a registration number available. Only applicable for organizations in New Zealand, and incorporated partnerships and government organizations in Australia. | getRegistrationNumberAbsent(): ?bool | setRegistrationNumberAbsent(?bool registrationNumberAbsent): void |
| `statusOfLegalProceeding` | [`?string(StatusOfLegalProceedingEnum)`](../../doc/models/status-of-legal-proceeding-enum.md) | Optional | The status of any current or past legal action taken against the legal entity.<br><br>Possible values: **noLegalActionsTaken**, **underJudicialAdministration**, **bankruptcyInsolvency**, **otherLegalMeasures**<br><br>If the value of this field is **noLegalActionsTaken**, then `dateOfInitiationOfLegalProceeding` is not required. Otherwise, it is required. | getStatusOfLegalProceeding(): ?string | setStatusOfLegalProceeding(?string statusOfLegalProceeding): void |
| `stockData` | [`?StockData2`](../../doc/models/stock-data-2.md) | Optional | Information about the organization's publicly traded stock. Provide this object only if `type` is **listedPublicCompany**. | getStockData(): ?StockData2 | setStockData(?StockData2 stockData): void |
| `support` | [`?Support1`](../../doc/models/support-1.md) | Optional | Support information for the legal entity. Required if you have a platform setup. | getSupport(): ?Support1 | setSupport(?Support1 support): void |
| `taxInformation` | [`?(TaxInformation[])`](../../doc/models/tax-information.md) | Optional | The tax information of the organization. | getTaxInformation(): ?array | setTaxInformation(?array taxInformation): void |
| `taxReportingClassification` | [`?TaxReportingClassification2`](../../doc/models/tax-reporting-classification-2.md) | Optional | The tax reporting classification (FATCA/CRS self-certification) of the organization. | getTaxReportingClassification(): ?TaxReportingClassification2 | setTaxReportingClassification(?TaxReportingClassification2 taxReportingClassification): void |
| `type` | [`?string(Type161Enum)`](../../doc/models/type-161-enum.md) | Optional | Type of organization.<br><br>Possible values: **associationIncorporated**, **governmentalOrganization**, **listedPublicCompany**, **nonProfit**, **partnershipIncorporated**, **privateCompany**. | getType(): ?string | setType(?string type): void |
| `vatAbsenceReason` | [`?string(VatAbsenceReasonEnum)`](../../doc/models/vat-absence-reason-enum.md) | Optional | The reason the organization has not provided a VAT number.<br><br>Possible values: **industryExemption**, **belowTaxThreshold**. | getVatAbsenceReason(): ?string | setVatAbsenceReason(?string vatAbsenceReason): void |
| `vatNumber` | `?string` | Optional | The organization's VAT number. | getVatNumber(): ?string | setVatNumber(?string vatNumber): void |
| `webData` | [`?WebData1`](../../doc/models/web-data-1.md) | Optional | The website and app URL of the legal entity. | getWebData(): ?WebData1 | setWebData(?WebData1 webData): void |

## Example

```php
use AdyenLib\Models\Builders\OrganizationBuilder;
use AdyenLib\Models\Builders\Address31Builder;

$organization = OrganizationBuilder::init(
    'legalName2',
    Address31Builder::init(
        'country4'
    )
        ->city('city0')
        ->postalCode('postalCode8')
        ->stateOrProvince('stateOrProvince8')
        ->street('street0')
        ->street2('street24')
        ->build()
)
    ->countryOfGoverningLaw('countryOfGoverningLaw8')
    ->dateOfIncorporation('dateOfIncorporation4')
    ->dateOfInitiationOfLegalProceeding('dateOfInitiationOfLegalProceeding6')
    ->description('description6')
    ->doingBusinessAs('doingBusinessAs4')
    ->build();
```

