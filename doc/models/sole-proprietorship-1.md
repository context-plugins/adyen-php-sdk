
# Sole Proprietorship 1

Information about the sole proprietorship. Required if `type` is **soleProprietorship**.

## Structure

`SoleProprietorship1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `countryOfGoverningLaw` | `string` | Required | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the governing country. | getCountryOfGoverningLaw(): string | setCountryOfGoverningLaw(string countryOfGoverningLaw): void |
| `dateOfIncorporation` | `?string` | Optional | The date when the legal arrangement was incorporated in YYYY-MM-DD format. | getDateOfIncorporation(): ?string | setDateOfIncorporation(?string dateOfIncorporation): void |
| `doingBusinessAs` | `?string` | Optional | The registered name, if different from the `name`. | getDoingBusinessAs(): ?string | setDoingBusinessAs(?string doingBusinessAs): void |
| `doingBusinessAsAbsent` | `?bool` | Optional | Set this to **true** if the legal arrangement does not have a `Doing business as` name. | getDoingBusinessAsAbsent(): ?bool | setDoingBusinessAsAbsent(?bool doingBusinessAsAbsent): void |
| `financialReports` | [`?(FinancialReport[])`](../../doc/models/financial-report.md) | Optional | The information from the financial report of the sole proprietorship. | getFinancialReports(): ?array | setFinancialReports(?array financialReports): void |
| `name` | `string` | Required | The legal name. | getName(): string | setName(string name): void |
| `principalPlaceOfBusiness` | [`?Address41`](../../doc/models/address-41.md) | Optional | The business address. Required if the principal place of business is different from the `registeredAddress`. | getPrincipalPlaceOfBusiness(): ?Address41 | setPrincipalPlaceOfBusiness(?Address41 principalPlaceOfBusiness): void |
| `registeredAddress` | [`Address51`](../../doc/models/address-51.md) | Required | The address registered at the registrar, such as the Chamber of Commerce. | getRegisteredAddress(): Address51 | setRegisteredAddress(Address51 registeredAddress): void |
| `registrationNumber` | `?string` | Optional | The registration number. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `taxAbsent` | `?bool` | Optional | The tax information is absent. | getTaxAbsent(): ?bool | setTaxAbsent(?bool taxAbsent): void |
| `taxInformation` | [`?(TaxInformation[])`](../../doc/models/tax-information.md) | Optional | The tax information of the entity. | getTaxInformation(): ?array | setTaxInformation(?array taxInformation): void |
| `vatAbsenceReason` | [`?string(VatAbsenceReason1Enum)`](../../doc/models/vat-absence-reason-1-enum.md) | Optional | The reason for not providing a VAT number.<br><br>Possible values: **industryExemption**, **belowTaxThreshold**. | getVatAbsenceReason(): ?string | setVatAbsenceReason(?string vatAbsenceReason): void |
| `vatNumber` | `?string` | Optional | The VAT number. | getVatNumber(): ?string | setVatNumber(?string vatNumber): void |

## Example

```php
use AdyenLib\Models\Builders\SoleProprietorship1Builder;
use AdyenLib\Models\Builders\Address51Builder;
use AdyenLib\Models\Builders\FinancialReportBuilder;
use AdyenLib\Models\Builders\Address41Builder;

$soleProprietorship1 = SoleProprietorship1Builder::init(
    'countryOfGoverningLaw2',
    'name2',
    Address51Builder::init(
        'country4'
    )
        ->city('city0')
        ->postalCode('postalCode8')
        ->stateOrProvince('stateOrProvince8')
        ->street('street0')
        ->street2('street24')
        ->build()
)
    ->dateOfIncorporation('dateOfIncorporation8')
    ->doingBusinessAs('doingBusinessAs0')
    ->doingBusinessAsAbsent(false)
    ->financialReports(
        [
            FinancialReportBuilder::init()
                ->annualTurnover('annualTurnover4')
                ->balanceSheetTotal('balanceSheetTotal2')
                ->currencyOfFinancialData('currencyOfFinancialData4')
                ->dateOfFinancialData('dateOfFinancialData8')
                ->employeeCount('employeeCount8')
                ->build(),
            FinancialReportBuilder::init()
                ->annualTurnover('annualTurnover4')
                ->balanceSheetTotal('balanceSheetTotal2')
                ->currencyOfFinancialData('currencyOfFinancialData4')
                ->dateOfFinancialData('dateOfFinancialData8')
                ->employeeCount('employeeCount8')
                ->build(),
            FinancialReportBuilder::init()
                ->annualTurnover('annualTurnover4')
                ->balanceSheetTotal('balanceSheetTotal2')
                ->currencyOfFinancialData('currencyOfFinancialData4')
                ->dateOfFinancialData('dateOfFinancialData8')
                ->employeeCount('employeeCount8')
                ->build()
        ]
    )
    ->principalPlaceOfBusiness(
        Address41Builder::init(
            'country6'
        )
            ->city('city8')
            ->postalCode('postalCode6')
            ->stateOrProvince('stateOrProvince0')
            ->street('street2')
            ->street2('street22')
            ->build()
    )
    ->build();
```

