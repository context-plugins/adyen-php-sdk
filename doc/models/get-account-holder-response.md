
# Get Account Holder Response

## Structure

`GetAccountHolderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `?string` | Optional | The code of the account holder. | getAccountHolderCode(): ?string | setAccountHolderCode(?string accountHolderCode): void |
| `accountHolderDetails` | [`?AccountHolderDetails3`](../../doc/models/account-holder-details-3.md) | Optional | Details of the account holder. | getAccountHolderDetails(): ?AccountHolderDetails3 | setAccountHolderDetails(?AccountHolderDetails3 accountHolderDetails): void |
| `accountHolderStatus` | [`?AccountHolderStatus3`](../../doc/models/account-holder-status-3.md) | Optional | The status of the account holder. | getAccountHolderStatus(): ?AccountHolderStatus3 | setAccountHolderStatus(?AccountHolderStatus3 accountHolderStatus): void |
| `accounts` | [`?(Account[])`](../../doc/models/account.md) | Optional | A list of the accounts under the account holder. | getAccounts(): ?array | setAccounts(?array accounts): void |
| `description` | `?string` | Optional | The description of the account holder. | getDescription(): ?string | setDescription(?string description): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `legalEntity` | [`?string(LegalEntity2Enum)`](../../doc/models/legal-entity-2-enum.md) | Optional | The legal entity of the account holder. | getLegalEntity(): ?string | setLegalEntity(?string legalEntity): void |
| `migrationData` | [`?MigrationData2`](../../doc/models/migration-data-2.md) | Optional | Details of the account holder migrated to the balance platform. | getMigrationData(): ?MigrationData2 | setMigrationData(?MigrationData2 migrationData): void |
| `primaryCurrency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes), with which the prospective account holder primarily deals. | getPrimaryCurrency(): ?string | setPrimaryCurrency(?string primaryCurrency): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `systemUpToDateTime` | `?DateTime` | Optional | The time that shows how up to date is the information in the response. | getSystemUpToDateTime(): ?\DateTime | setSystemUpToDateTime(?\DateTime systemUpToDateTime): void |
| `verification` | [`?KYCVerificationResult1`](../../doc/models/kyc-verification-result-1.md) | Optional | The details of KYC Verification of the account holder. | getVerification(): ?KYCVerificationResult1 | setVerification(?KYCVerificationResult1 verification): void |
| `verificationProfile` | `?string` | Optional | The identifier of the profile that applies to this entity. | getVerificationProfile(): ?string | setVerificationProfile(?string verificationProfile): void |

## Example

```php
use AdyenLib\Models\Builders\GetAccountHolderResponseBuilder;
use AdyenLib\Models\Builders\AccountHolderDetails3Builder;
use AdyenLib\Models\Builders\ViasAddress9Builder;
use AdyenLib\Models\Builders\BankAccountDetailBuilder;
use AdyenLib\Models\Builders\BusinessDetails3Builder;
use AdyenLib\Models\Builders\UltimateParentCompanyBuilder;
use AdyenLib\Models\Builders\ViasAddress1Builder;
use AdyenLib\Models\Builders\UltimateParentCompanyBusinessDetails2Builder;
use AdyenLib\Models\Builders\ShareholderContactBuilder;
use AdyenLib\Models\Builders\ViasAddress2Builder;
use AdyenLib\Models\Builders\ViasName1Builder;
use AdyenLib\Models\GenderEnum;
use AdyenLib\Models\Builders\AccountHolderStatus3Builder;
use AdyenLib\Models\Status12Enum;
use AdyenLib\Models\Builders\AccountEventBuilder;
use AdyenLib\Models\EventEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AccountPayoutState2Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\AccountProcessingState2Builder;
use AdyenLib\Models\Builders\AccountBuilder;

$getAccountHolderResponse = GetAccountHolderResponseBuilder::init()
    ->accountHolderCode('accountHolderCode4')
    ->accountHolderDetails(
        AccountHolderDetails3Builder::init(
            ViasAddress9Builder::init(
                'country0'
            )
                ->city('city6')
                ->houseNumberOrName('houseNumberOrName4')
                ->postalCode('postalCode8')
                ->stateOrProvince('stateOrProvince4')
                ->street('street6')
                ->build()
        )
            ->bankAccountDetails(
                [
                    BankAccountDetailBuilder::init()
                        ->accountNumber('accountNumber8')
                        ->accountType('accountType4')
                        ->bankAccountName('bankAccountName4')
                        ->bankAccountReference('bankAccountReference4')
                        ->bankAccountUUID('bankAccountUUID0')
                        ->build(),
                    BankAccountDetailBuilder::init()
                        ->accountNumber('accountNumber8')
                        ->accountType('accountType4')
                        ->bankAccountName('bankAccountName4')
                        ->bankAccountReference('bankAccountReference4')
                        ->bankAccountUUID('bankAccountUUID0')
                        ->build(),
                    BankAccountDetailBuilder::init()
                        ->accountNumber('accountNumber8')
                        ->accountType('accountType4')
                        ->bankAccountName('bankAccountName4')
                        ->bankAccountReference('bankAccountReference4')
                        ->bankAccountUUID('bankAccountUUID0')
                        ->build()
                ]
            )
            ->bankAggregatorDataReference('bankAggregatorDataReference6')
            ->businessDetails(
                BusinessDetails3Builder::init()
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
            ->email('email2')
            ->fullPhoneNumber('fullPhoneNumber8')
            ->build()
    )
    ->accountHolderStatus(
        AccountHolderStatus3Builder::init(
            Status12Enum::INACTIVE
        )
            ->events(
                [
                    AccountEventBuilder::init()
                        ->event(EventEnum::INACTIVATEACCOUNT)
                        ->executionDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                        ->reason('reason6')
                        ->build()
                ]
            )
            ->payoutState(
                AccountPayoutState2Builder::init()
                    ->allowPayout(false)
                    ->disableReason('disableReason2')
                    ->disabled(false)
                    ->notAllowedReason('notAllowedReason4')
                    ->payoutLimit(
                        AmountBuilder::init(
                            'currency8',
                            88
                        )->build()
                    )->build()
            )
            ->processingState(
                AccountProcessingState2Builder::init()
                    ->disableReason('disableReason2')
                    ->disabled(false)
                    ->processedFrom(
                        AmountBuilder::init(
                            'currency4',
                            148
                        )->build()
                    )
                    ->processedTo(
                        AmountBuilder::init(
                            'currency2',
                            54
                        )->build()
                    )
                    ->tierNumber(156)
                    ->build()
            )
            ->statusReason('statusReason8')
            ->build()
    )
    ->accounts(
        [
            AccountBuilder::init()
                ->accountCode('accountCode0')
                ->bankAccountUUID('bankAccountUUID6')
                ->beneficiaryAccount('beneficiaryAccount2')
                ->beneficiaryMerchantReference('beneficiaryMerchantReference2')
                ->description('description0')
                ->build(),
            AccountBuilder::init()
                ->accountCode('accountCode0')
                ->bankAccountUUID('bankAccountUUID6')
                ->beneficiaryAccount('beneficiaryAccount2')
                ->beneficiaryMerchantReference('beneficiaryMerchantReference2')
                ->description('description0')
                ->build()
        ]
    )
    ->description('description0')
    ->build();
```

