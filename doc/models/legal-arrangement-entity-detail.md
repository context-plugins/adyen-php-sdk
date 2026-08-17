
# Legal Arrangement Entity Detail

## Structure

`LegalArrangementEntityDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?ViasAddress5`](../../doc/models/vias-address-5.md) | Optional | The address of the entity. | getAddress(): ?ViasAddress5 | setAddress(?ViasAddress5 address): void |
| `businessDetails` | [`?BusinessDetails1`](../../doc/models/business-details-1.md) | Optional | Required when creating an entity with `legalEntityType` **Business**, **NonProfit**, **PublicCompany**, or **Partnership**. | getBusinessDetails(): ?BusinessDetails1 | setBusinessDetails(?BusinessDetails1 businessDetails): void |
| `email` | `?string` | Optional | The e-mail address of the entity. | getEmail(): ?string | setEmail(?string email): void |
| `fullPhoneNumber` | `?string` | Optional | The phone number of the contact provided as a single string.  It will be handled as a landline phone.<br>**Examples:** "0031 6 11 22 33 44", "+316/1122-3344", "(0031) 611223344" | getFullPhoneNumber(): ?string | setFullPhoneNumber(?string fullPhoneNumber): void |
| `individualDetails` | [`?IndividualDetails1`](../../doc/models/individual-details-1.md) | Optional | Required when creating an entity with `legalEntityType` **Individual**. | getIndividualDetails(): ?IndividualDetails1 | setIndividualDetails(?IndividualDetails1 individualDetails): void |
| `legalArrangementEntityCode` | `?string` | Optional | Adyen-generated unique alphanumeric identifier (UUID) for the entry, returned in the response when you create a legal arrangement entity.<br>Use only when updating an account holder. If you include this field when creating an account holder, the request will fail. | getLegalArrangementEntityCode(): ?string | setLegalArrangementEntityCode(?string legalArrangementEntityCode): void |
| `legalArrangementEntityReference` | `?string` | Optional | Your reference for the legal arrangement entity. | getLegalArrangementEntityReference(): ?string | setLegalArrangementEntityReference(?string legalArrangementEntityReference): void |
| `legalArrangementMembers` | [`?(string(LegalArrangementMemberEnum)[])`](../../doc/models/legal-arrangement-member-enum.md) | Optional | An array containing the roles of the entity in the legal arrangement.<br><br>The possible values depend on the legal arrangement `type`.<br><br>- For `type` **Association**: **ControllingPerson** and **Shareholder**.<br><br>- For `type` **Partnership**: **Partner** and **Shareholder**.<br><br>- For `type` **Trust**: **Trustee**, **Settlor**, **Protector**, **Beneficiary**,  and **Shareholder**. | getLegalArrangementMembers(): ?array | setLegalArrangementMembers(?array legalArrangementMembers): void |
| `legalEntityType` | [`?string(LegalEntityTypeEnum)`](../../doc/models/legal-entity-type-enum.md) | Optional | The legal entity type.<br><br>Possible values: **Business**, **Individual**, **NonProfit**, **PublicCompany**, or **Partnership**. | getLegalEntityType(): ?string | setLegalEntityType(?string legalEntityType): void |
| `phoneNumber` | [`?ViasPhoneNumber2`](../../doc/models/vias-phone-number-2.md) | Optional | The phone number of the entity. | getPhoneNumber(): ?ViasPhoneNumber2 | setPhoneNumber(?ViasPhoneNumber2 phoneNumber): void |
| `webAddress` | `?string` | Optional | The URL of the website of the contact. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
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

$legalArrangementEntityDetail = LegalArrangementEntityDetailBuilder::init()
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
    ->email('email6')
    ->fullPhoneNumber('fullPhoneNumber4')
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
    ->build();
```

