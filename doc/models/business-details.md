
# Business Details

## Structure

`BusinessDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `doingBusinessAs` | `?string` | Optional | The registered name of the company (if it differs from the legal name of the company). | getDoingBusinessAs(): ?string | setDoingBusinessAs(?string doingBusinessAs): void |
| `legalBusinessName` | `?string` | Optional | The legal name of the company. | getLegalBusinessName(): ?string | setLegalBusinessName(?string legalBusinessName): void |
| `listedUltimateParentCompany` | [`?(UltimateParentCompany[])`](../../doc/models/ultimate-parent-company.md) | Optional | Information about the parent public company. Required if the account holder is 100% owned by a publicly listed company. | getListedUltimateParentCompany(): ?array | setListedUltimateParentCompany(?array listedUltimateParentCompany): void |
| `registrationNumber` | `?string` | Optional | The registration number of the company. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `shareholders` | [`?(ShareholderContact[])`](../../doc/models/shareholder-contact.md) | Optional | Array containing information about individuals associated with the account holder either through ownership or control. For details about how you can identify them, refer to [our verification guide](https://docs.adyen.com/classic-platforms/verification-process#identify-ubos). | getShareholders(): ?array | setShareholders(?array shareholders): void |
| `signatories` | [`?(SignatoryContact[])`](../../doc/models/signatory-contact.md) | Optional | Signatories associated with the company.<br>Each array entry should represent one signatory. | getSignatories(): ?array | setSignatories(?array signatories): void |
| `stockExchange` | `?string` | Optional | Market Identifier Code (MIC). | getStockExchange(): ?string | setStockExchange(?string stockExchange): void |
| `stockNumber` | `?string` | Optional | International Securities Identification Number (ISIN). | getStockNumber(): ?string | setStockNumber(?string stockNumber): void |
| `stockTicker` | `?string` | Optional | Stock Ticker symbol. | getStockTicker(): ?string | setStockTicker(?string stockTicker): void |
| `taxId` | `?string` | Optional | The tax ID of the company. | getTaxId(): ?string | setTaxId(?string taxId): void |

## Example

```php
use AdyenLib\Models\Builders\BusinessDetailsBuilder;
use AdyenLib\Models\Builders\UltimateParentCompanyBuilder;
use AdyenLib\Models\Builders\ViasAddress1Builder;
use AdyenLib\Models\Builders\UltimateParentCompanyBusinessDetails2Builder;
use AdyenLib\Models\Builders\ShareholderContactBuilder;
use AdyenLib\Models\Builders\ViasAddress2Builder;
use AdyenLib\Models\Builders\ViasName1Builder;
use AdyenLib\Models\GenderEnum;

$businessDetails = BusinessDetailsBuilder::init()
    ->doingBusinessAs('doingBusinessAs6')
    ->legalBusinessName('legalBusinessName8')
    ->listedUltimateParentCompany(
        [
            UltimateParentCompanyBuilder::init()
                ->address(
                    ViasAddress1Builder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->houseNumberOrName('houseNumberOrName4')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->street('street6')
                        ->build()
                )
                ->businessDetails(
                    UltimateParentCompanyBusinessDetails2Builder::init()
                        ->legalBusinessName('legalBusinessName8')
                        ->registrationNumber('registrationNumber6')
                        ->stockExchange('stockExchange4')
                        ->stockNumber('stockNumber6')
                        ->stockTicker('stockTicker6')
                        ->build()
                )
                ->ultimateParentCompanyCode('ultimateParentCompanyCode2')
                ->build(),
            UltimateParentCompanyBuilder::init()
                ->address(
                    ViasAddress1Builder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->houseNumberOrName('houseNumberOrName4')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->street('street6')
                        ->build()
                )
                ->businessDetails(
                    UltimateParentCompanyBusinessDetails2Builder::init()
                        ->legalBusinessName('legalBusinessName8')
                        ->registrationNumber('registrationNumber6')
                        ->stockExchange('stockExchange4')
                        ->stockNumber('stockNumber6')
                        ->stockTicker('stockTicker6')
                        ->build()
                )
                ->ultimateParentCompanyCode('ultimateParentCompanyCode2')
                ->build()
        ]
    )
    ->registrationNumber('registrationNumber6')
    ->shareholders(
        [
            ShareholderContactBuilder::init()
                ->address(
                    ViasAddress2Builder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->houseNumberOrName('houseNumberOrName4')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->street('street6')
                        ->build()
                )
                ->email('email8')
                ->fullPhoneNumber('fullPhoneNumber2')
                ->jobTitle('jobTitle2')
                ->name(
                    ViasName1Builder::init()
                        ->firstName('firstName4')
                        ->gender(GenderEnum::MALE)
                        ->infix('infix4')
                        ->lastName('lastName4')
                        ->build()
                )
                ->build(),
            ShareholderContactBuilder::init()
                ->address(
                    ViasAddress2Builder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->houseNumberOrName('houseNumberOrName4')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->street('street6')
                        ->build()
                )
                ->email('email8')
                ->fullPhoneNumber('fullPhoneNumber2')
                ->jobTitle('jobTitle2')
                ->name(
                    ViasName1Builder::init()
                        ->firstName('firstName4')
                        ->gender(GenderEnum::MALE)
                        ->infix('infix4')
                        ->lastName('lastName4')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

