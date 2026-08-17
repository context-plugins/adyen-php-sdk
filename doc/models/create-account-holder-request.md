
# Create Account Holder Request

## Structure

`CreateAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | Your unique identifier for the prospective account holder.<br>The length must be between three (3) and fifty (50) characters long. Only letters, digits, and hyphens (-) are allowed. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `accountHolderDetails` | [`AccountHolderDetails1`](../../doc/models/account-holder-details-1.md) | Required | The details of the prospective account holder. | getAccountHolderDetails(): AccountHolderDetails1 | setAccountHolderDetails(AccountHolderDetails1 accountHolderDetails): void |
| `createDefaultAccount` | `?bool` | Optional | If set to **true**, an account with the default options is automatically created for the account holder.<br>By default, this field is set to **true**. | getCreateDefaultAccount(): ?bool | setCreateDefaultAccount(?bool createDefaultAccount): void |
| `description` | `?string` | Optional | A description of the prospective account holder, maximum 256 characters. You can use alphanumeric characters (A-Z, a-z, 0-9), white spaces, and underscores `_`. | getDescription(): ?string | setDescription(?string description): void |
| `legalEntity` | [`string(LegalEntityEnum)`](../../doc/models/legal-entity-enum.md) | Required | The legal entity type of the account holder. This determines the information that should be provided in the request.<br><br>Possible values: **Business**, **Individual**, or **NonProfit**.<br><br>* If set to **Business** or **NonProfit**, then `accountHolderDetails.businessDetails` must be provided, with at least one entry in the `accountHolderDetails.businessDetails.shareholders` list.<br><br>* If set to **Individual**, then `accountHolderDetails.individualDetails` must be provided. | getLegalEntity(): string | setLegalEntity(string legalEntity): void |
| `primaryCurrency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes), with which the prospective account holder primarily deals. | getPrimaryCurrency(): ?string | setPrimaryCurrency(?string primaryCurrency): void |
| `processingTier` | `?int` | Optional | The starting [processing tier](https://docs.adyen.com/classic-platforms/onboarding-and-verification/precheck-kyc-information) for the prospective account holder. | getProcessingTier(): ?int | setProcessingTier(?int processingTier): void |
| `verificationProfile` | `?string` | Optional | The identifier of the profile that applies to this entity. | getVerificationProfile(): ?string | setVerificationProfile(?string verificationProfile): void |

## Example

```php
use AdyenLib\Models\Builders\CreateAccountHolderRequestBuilder;
use AdyenLib\Models\Builders\AccountHolderDetails1Builder;
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
use AdyenLib\Models\LegalEntityEnum;

$createAccountHolderRequest = CreateAccountHolderRequestBuilder::init(
    'accountHolderCode8',
    AccountHolderDetails1Builder::init(
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
        ->build(),
    LegalEntityEnum::BUSINESS
)
    ->createDefaultAccount(false)
    ->description('description2')
    ->primaryCurrency('primaryCurrency4')
    ->processingTier(44)
    ->verificationProfile('verificationProfile6')
    ->build();
```

