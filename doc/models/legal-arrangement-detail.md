
# Legal Arrangement Detail

## Structure

`LegalArrangementDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`ViasAddress4`](../../doc/models/vias-address-4.md) | Required | The address of the legal arrangement. | getAddress(): ViasAddress4 | setAddress(ViasAddress4 address): void |
| `legalArrangementCode` | `?string` | Optional | Adyen-generated unique alphanumeric identifier (UUID) for the entry, returned in the response when you create a legal arrangement.<br>Use only when updating an account holder. If you include this field when creating an account holder, the request will fail. | getLegalArrangementCode(): ?string | setLegalArrangementCode(?string legalArrangementCode): void |
| `legalArrangementEntities` | [`?(LegalArrangementEntityDetail[])`](../../doc/models/legal-arrangement-entity-detail.md) | Optional | An array containing information about other entities that are part of the legal arrangement. | getLegalArrangementEntities(): ?array | setLegalArrangementEntities(?array legalArrangementEntities): void |
| `legalArrangementReference` | `?string` | Optional | Your reference for the legal arrangement. Must be between 3 to 128 characters. | getLegalArrangementReference(): ?string | setLegalArrangementReference(?string legalArrangementReference): void |
| `legalForm` | [`?string(LegalFormEnum)`](../../doc/models/legal-form-enum.md) | Optional | The form of legal arrangement. Required if `type` is **Trust** or **Partnership**.<br><br>The possible values depend on the `type`.<br><br>- For `type` **Trust**:  **CashManagementTrust**, **CorporateUnitTrust**, **DeceasedEstate**, **DiscretionaryInvestmentTrust**, **DiscretionaryServicesManagementTrust**, **DiscretionaryTradingTrust**, **FirstHomeSaverAccountsTrust**, **FixedTrust**, **FixedUnitTrust**, **HybridTrust**, **ListedPublicUnitTrust**, **OtherTrust**, **PooledSuperannuationTrust**, **PublicTradingTrust**, or **UnlistedPublicUnitTrust**.<br><br>- For `type` **Partnership**: **LimitedPartnership**, **FamilyPartnership**, or **OtherPartnership** | getLegalForm(): ?string | setLegalForm(?string legalForm): void |
| `name` | `string` | Required | The legal name of the legal arrangement. Minimum length: 3 characters. | getName(): string | setName(string name): void |
| `registrationNumber` | `?string` | Optional | The registration number of the legal arrangement. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `taxNumber` | `?string` | Optional | The tax identification number of the legal arrangement. | getTaxNumber(): ?string | setTaxNumber(?string taxNumber): void |
| `type` | [`string(Type110Enum)`](../../doc/models/type-110-enum.md) | Required | The [type of legal arrangement](https://docs.adyen.com/classic-platforms/verification-process/legal-arrangements#types-of-legal-arrangements).<br><br>Possible values:<br><br>- **Association**<br><br>- **Partnership**<br><br>- **SoleProprietorship**<br><br>- **Trust** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\LegalArrangementDetailBuilder;
use AdyenLib\Models\Builders\ViasAddress4Builder;
use AdyenLib\Models\Type110Enum;
use AdyenLib\Models\Builders\LegalArrangementEntityDetailBuilder;
use AdyenLib\Models\Builders\ViasAddress5Builder;
use AdyenLib\Models\Builders\BusinessDetails1Builder;
use AdyenLib\Models\Builders\UltimateParentCompanyBuilder;
use AdyenLib\Models\Builders\ViasAddress1Builder;
use AdyenLib\Models\Builders\UltimateParentCompanyBusinessDetails2Builder;
use AdyenLib\Models\Builders\ShareholderContactBuilder;
use AdyenLib\Models\Builders\ViasAddress2Builder;
use AdyenLib\Models\Builders\ViasName1Builder;
use AdyenLib\Models\GenderEnum;
use AdyenLib\Models\Builders\PersonalDocumentDataBuilder;
use AdyenLib\Models\Type15Enum;
use AdyenLib\Models\Builders\IndividualDetails1Builder;
use AdyenLib\Models\Builders\ViasName2Builder;
use AdyenLib\Models\Builders\ViasPersonalData2Builder;
use AdyenLib\Models\LegalFormEnum;

$legalArrangementDetail = LegalArrangementDetailBuilder::init(
    ViasAddress4Builder::init(
        'country0'
    )
        ->city('city6')
        ->houseNumberOrName('houseNumberOrName4')
        ->postalCode('postalCode8')
        ->stateOrProvince('stateOrProvince4')
        ->street('street6')
        ->build(),
    'name2',
    Type110Enum::SOLEPROPRIETORSHIP
)
    ->legalArrangementCode('legalArrangementCode4')
    ->legalArrangementEntities(
        [
            LegalArrangementEntityDetailBuilder::init()
                ->address(
                    ViasAddress5Builder::init(
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
                    BusinessDetails1Builder::init()
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
                        ->build()
                )
                ->email('email4')
                ->fullPhoneNumber('fullPhoneNumber6')
                ->individualDetails(
                    IndividualDetails1Builder::init()
                        ->name(
                            ViasName2Builder::init()
                                ->firstName('firstName4')
                                ->gender(GenderEnum::MALE)
                                ->infix('infix4')
                                ->lastName('lastName4')
                                ->build()
                        )
                        ->personalData(
                            ViasPersonalData2Builder::init()
                                ->dateOfBirth('dateOfBirth2')
                                ->documentData(
                                    [
                                        PersonalDocumentDataBuilder::init(
                                            Type15Enum::ID
                                        )
                                            ->expirationDate('expirationDate8')
                                            ->issuerCountry('issuerCountry0')
                                            ->issuerState('issuerState0')
                                            ->number('number8')
                                            ->build(),
                                        PersonalDocumentDataBuilder::init(
                                            Type15Enum::ID
                                        )
                                            ->expirationDate('expirationDate8')
                                            ->issuerCountry('issuerCountry0')
                                            ->issuerState('issuerState0')
                                            ->number('number8')
                                            ->build(),
                                        PersonalDocumentDataBuilder::init(
                                            Type15Enum::ID
                                        )
                                            ->expirationDate('expirationDate8')
                                            ->issuerCountry('issuerCountry0')
                                            ->issuerState('issuerState0')
                                            ->number('number8')
                                            ->build()
                                    ]
                                )
                                ->nationality('nationality4')
                                ->build()
                        )
                        ->build()
                )
                ->build()
        ]
    )
    ->legalArrangementReference('legalArrangementReference6')
    ->legalForm(LegalFormEnum::DISCRETIONARYSERVICESMANAGEMENTTRUST)
    ->registrationNumber('registrationNumber0')
    ->build();
```

