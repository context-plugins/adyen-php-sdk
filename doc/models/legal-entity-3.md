
# Legal Entity 3

## Structure

`LegalEntity3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capabilities` | [`?array<string,LegalEntityCapability>`](../../doc/models/legal-entity-capability.md) | Optional | Contains key-value pairs that specify the actions that the legal entity can do in your platform.The key is a capability required for your integration. For example, **issueCard** for Issuing. The value is an object containing the settings for the capability. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `documentDetails` | [`?(DocumentReference[])`](../../doc/models/document-reference.md) | Optional | List of documents uploaded for the legal entity. | getDocumentDetails(): ?array | setDocumentDetails(?array documentDetails): void |
| `documents` | [`?(UploadAndroidAppResponse[])`](../../doc/models/upload-android-app-response.md) | Optional | List of documents uploaded for the legal entity. | getDocuments(): ?array | setDocuments(?array documents): void |
| `entityAssociations` | [`?(LegalEntityAssociation[])`](../../doc/models/legal-entity-association.md) | Optional | List of legal entities associated with the current legal entity.<br>For example, ultimate beneficial owners associated with an organization through ownership or control, or as signatories. | getEntityAssociations(): ?array | setEntityAssociations(?array entityAssociations): void |
| `id` | `string` | Required, Read-only | The unique identifier of the legal entity. | getId(): string | setId(string id): void |
| `individual` | [`?Individual1`](../../doc/models/individual-1.md) | Optional | Information about the individual. Required if `type` is **individual**. | getIndividual(): ?Individual1 | setIndividual(?Individual1 individual): void |
| `organization` | [`?Organization1`](../../doc/models/organization-1.md) | Optional | Information about the organization. Required if `type` is **organization**. | getOrganization(): ?Organization1 | setOrganization(?Organization1 organization): void |
| `problems` | [`?(CapabilityProblem1[])`](../../doc/models/capability-problem-1.md) | Optional | List of verification errors related to capabilities for the legal entity. | getProblems(): ?array | setProblems(?array problems): void |
| `reference` | `?string` | Optional | Your reference for the legal entity, maximum 150 characters.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `soleProprietorship` | [`?SoleProprietorship1`](../../doc/models/sole-proprietorship-1.md) | Optional | Information about the sole proprietorship. Required if `type` is **soleProprietorship**. | getSoleProprietorship(): ?SoleProprietorship1 | setSoleProprietorship(?SoleProprietorship1 soleProprietorship): void |
| `transferInstruments` | [`?(TransferInstrumentReference[])`](../../doc/models/transfer-instrument-reference.md) | Optional, Read-only | List of transfer instruments that the legal entity owns. | getTransferInstruments(): ?array | setTransferInstruments(?array transferInstruments): void |
| `trust` | [`?Trust1`](../../doc/models/trust-1.md) | Optional | Information about the trust. Required if `type` is **trust**. | getTrust(): ?Trust1 | setTrust(?Trust1 trust): void |
| `type` | [`?string(Type182Enum)`](../../doc/models/type-182-enum.md) | Optional | The type of legal entity.<br><br>Possible values: **individual**, **organization**, **soleProprietorship**, or **trust**. | getType(): ?string | setType(?string type): void |
| `unincorporatedPartnership` | [`?UnincorporatedPartnership1`](../../doc/models/unincorporated-partnership-1.md) | Optional | Information about the unincorporated partnership. Required if `type` is **unincorporatedPartnership**. | getUnincorporatedPartnership(): ?UnincorporatedPartnership1 | setUnincorporatedPartnership(?UnincorporatedPartnership1 unincorporatedPartnership): void |
| `verificationDeadlines` | [`?(VerificationDeadline[])`](../../doc/models/verification-deadline.md) | Optional, Read-only | List of verification deadlines and the capabilities that will be disallowed if verification errors are not resolved. | getVerificationDeadlines(): ?array | setVerificationDeadlines(?array verificationDeadlines): void |
| `verificationPlan` | `?string` | Optional | A key-value pair that specifies the verification process for a legal entity. Set to **upfront** for upfront verification for [marketplaces](https://docs.adyen.com/marketplaces/verification-overview/verification-types/#upfront-verification). | getVerificationPlan(): ?string | setVerificationPlan(?string verificationPlan): void |

## Example

```php
use AdyenLib\Models\Builders\LegalEntity3Builder;
use AdyenLib\Models\Builders\LegalEntityCapabilityBuilder;
use AdyenLib\Models\Builders\CapabilitySettings11Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;
use AdyenLib\Models\Builders\DocumentReferenceBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\UploadAndroidAppResponseBuilder;
use AdyenLib\Models\Builders\LegalEntityAssociationBuilder;
use AdyenLib\Models\Type142Enum;
use AdyenLib\Models\Builders\Individual1Builder;
use AdyenLib\Models\Builders\Name23Builder;
use AdyenLib\Models\Builders\Address13Builder;
use AdyenLib\Models\Builders\BirthData1Builder;
use AdyenLib\Models\Builders\IdentificationData1Builder;
use AdyenLib\Models\Type132Enum;
use AdyenLib\Models\Builders\PhoneNumber2Builder;

$legalEntity3 = LegalEntity3Builder::init(
    ''
)
    ->capabilities(
        [
            'key0' => LegalEntityCapabilityBuilder::init()
                ->allowedSettings(
                    CapabilitySettings11Builder::init()
                        ->amountPerIndustry(
                            [
                                'key0' => PatchableAmountDTOBuilder::init()
                                    ->currency('currency8')
                                    ->value(56)
                                    ->build(),
                                'key1' => PatchableAmountDTOBuilder::init()
                                    ->currency('currency8')
                                    ->value(56)
                                    ->build()
                            ]
                        )
                        ->authorizedCardUsers(false)
                        ->fundingSource(
                            [
                                FundingSourceEnum::CREDIT,
                                FundingSourceEnum::DEBIT,
                                FundingSourceEnum::PREPAID
                            ]
                        )
                        ->interval(IntervalEnum::DAILY)
                        ->maxAmount(
                            PatchableAmountDTOBuilder::init()
                                ->currency('currency4')
                                ->value(160)
                                ->build()
                        )
                        ->build()
                )
                ->build(),
            'key1' => LegalEntityCapabilityBuilder::init()
                ->allowedSettings(
                    CapabilitySettings11Builder::init()
                        ->amountPerIndustry(
                            [
                                'key0' => PatchableAmountDTOBuilder::init()
                                    ->currency('currency8')
                                    ->value(56)
                                    ->build(),
                                'key1' => PatchableAmountDTOBuilder::init()
                                    ->currency('currency8')
                                    ->value(56)
                                    ->build()
                            ]
                        )
                        ->authorizedCardUsers(false)
                        ->fundingSource(
                            [
                                FundingSourceEnum::CREDIT,
                                FundingSourceEnum::DEBIT,
                                FundingSourceEnum::PREPAID
                            ]
                        )
                        ->interval(IntervalEnum::DAILY)
                        ->maxAmount(
                            PatchableAmountDTOBuilder::init()
                                ->currency('currency4')
                                ->value(160)
                                ->build()
                        )
                        ->build()
                )
                ->build(),
            'key2' => LegalEntityCapabilityBuilder::init()
                ->allowedSettings(
                    CapabilitySettings11Builder::init()
                        ->amountPerIndustry(
                            [
                                'key0' => PatchableAmountDTOBuilder::init()
                                    ->currency('currency8')
                                    ->value(56)
                                    ->build(),
                                'key1' => PatchableAmountDTOBuilder::init()
                                    ->currency('currency8')
                                    ->value(56)
                                    ->build()
                            ]
                        )
                        ->authorizedCardUsers(false)
                        ->fundingSource(
                            [
                                FundingSourceEnum::CREDIT,
                                FundingSourceEnum::DEBIT,
                                FundingSourceEnum::PREPAID
                            ]
                        )
                        ->interval(IntervalEnum::DAILY)
                        ->maxAmount(
                            PatchableAmountDTOBuilder::init()
                                ->currency('currency4')
                                ->value(160)
                                ->build()
                        )
                        ->build()
                )
                ->build()
        ]
    )
    ->documentDetails(
        [
            DocumentReferenceBuilder::init()
                ->active(false)
                ->description('description4')
                ->fileName('fileName8')
                ->id('id4')
                ->modificationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->build()
        ]
    )
    ->documents(
        [
            UploadAndroidAppResponseBuilder::init()
                ->id('id4')
                ->build(),
            UploadAndroidAppResponseBuilder::init()
                ->id('id4')
                ->build(),
            UploadAndroidAppResponseBuilder::init()
                ->id('id4')
                ->build()
        ]
    )
    ->entityAssociations(
        [
            LegalEntityAssociationBuilder::init(
                'legalEntityId4',
                Type142Enum::IMMEDIATEPARENTCOMPANY
            )
                ->jobTitle('jobTitle4')
                ->nominee(false)
                ->build(),
            LegalEntityAssociationBuilder::init(
                'legalEntityId4',
                Type142Enum::IMMEDIATEPARENTCOMPANY
            )
                ->jobTitle('jobTitle4')
                ->nominee(false)
                ->build()
        ]
    )
    ->individual(
        Individual1Builder::init(
            Name23Builder::init(
                'firstName4',
                'lastName4'
            )
                ->infix('infix4')
                ->build(),
            Address13Builder::init(
                'country6'
            )
                ->city('city2')
                ->postalCode('postalCode4')
                ->stateOrProvince('stateOrProvince0')
                ->street('street2')
                ->street2('street28')
                ->build()
        )
            ->birthData(
                BirthData1Builder::init()
                    ->dateOfBirth('dateOfBirth8')
                    ->build()
            )
            ->email('email0')
            ->identificationData(
                IdentificationData1Builder::init(
                    Type132Enum::NATIONALIDNUMBER
                )
                    ->cardNumber('cardNumber6')
                    ->expiryDate('expiryDate8')
                    ->issuerCountry('issuerCountry6')
                    ->issuerState('issuerState6')
                    ->nationalIdExempt(false)
                    ->build()
            )
            ->nationality('nationality4')
            ->phone(
                PhoneNumber2Builder::init(
                    'number8'
                )
                    ->type('type0')
                    ->build()
            )
            ->build()
    )
    ->build();
```

