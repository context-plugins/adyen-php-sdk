
# Update Account Holder Request

## Structure

`UpdateAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the Account Holder to be updated. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `accountHolderDetails` | [`?AccountHolderDetails4`](../../doc/models/account-holder-details-4.md) | Optional | The details to which the Account Holder should be updated.<br><br>Required if a processingTier is not provided. | getAccountHolderDetails(): ?AccountHolderDetails4 | setAccountHolderDetails(?AccountHolderDetails4 accountHolderDetails): void |
| `description` | `?string` | Optional | A description of the account holder, maximum 256 characters. You can use alphanumeric characters (A-Z, a-z, 0-9), white spaces, and underscores `_`. | getDescription(): ?string | setDescription(?string description): void |
| `legalEntity` | [`?string(LegalEntityEnum)`](../../doc/models/legal-entity-enum.md) | Optional | The legal entity type of the account holder. This determines the information that should be provided in the request.<br><br>Possible values: **Business**, **Individual**, or **NonProfit**.<br><br>* If set to **Business** or **NonProfit**, then `accountHolderDetails.businessDetails` must be provided, with at least one entry in the `accountHolderDetails.businessDetails.shareholders` list.<br><br>* If set to **Individual**, then `accountHolderDetails.individualDetails` must be provided. | getLegalEntity(): ?string | setLegalEntity(?string legalEntity): void |
| `primaryCurrency` | `?string` | Optional | The primary three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes), to which the account holder should be updated. | getPrimaryCurrency(): ?string | setPrimaryCurrency(?string primaryCurrency): void |
| `processingTier` | `?int` | Optional | The processing tier to which the Account Holder should be updated.<br><br>> The processing tier can not be lowered through this request.<br><br>> Required if accountHolderDetails are not provided. | getProcessingTier(): ?int | setProcessingTier(?int processingTier): void |
| `verificationProfile` | `?string` | Optional | The identifier of the profile that applies to this entity. | getVerificationProfile(): ?string | setVerificationProfile(?string verificationProfile): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateAccountHolderRequestBuilder;
use AdyenLib\Models\Builders\AccountHolderDetails4Builder;
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

$updateAccountHolderRequest = UpdateAccountHolderRequestBuilder::init(
    'accountHolderCode0'
)
    ->accountHolderDetails(
        AccountHolderDetails4Builder::init(
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
    ->description('description4')
    ->legalEntity(LegalEntityEnum::NONPROFIT)
    ->primaryCurrency('primaryCurrency6')
    ->processingTier(72)
    ->build();
```

