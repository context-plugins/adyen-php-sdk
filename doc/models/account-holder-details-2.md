
# Account Holder Details 2

Details of the new account holder.

## Structure

`AccountHolderDetails2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`ViasAddress9`](../../doc/models/vias-address-9.md) | Required | The address of the account holder. | getAddress(): ViasAddress9 | setAddress(ViasAddress9 address): void |
| `bankAccountDetails` | [`?(BankAccountDetail[])`](../../doc/models/bank-account-detail.md) | Optional | Array of bank accounts associated with the account holder. For details about the required `bankAccountDetail` fields, see [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information). | getBankAccountDetails(): ?array | setBankAccountDetails(?array bankAccountDetails): void |
| `bankAggregatorDataReference` | `?string` | Optional | The opaque reference value returned by the Adyen API during bank account login. | getBankAggregatorDataReference(): ?string | setBankAggregatorDataReference(?string bankAggregatorDataReference): void |
| `businessDetails` | [`?BusinessDetails3`](../../doc/models/business-details-3.md) | Optional | Details about the business or nonprofit account holder.<br>Required when creating an account holder with `legalEntity` **Business** or **NonProfit**. | getBusinessDetails(): ?BusinessDetails3 | setBusinessDetails(?BusinessDetails3 businessDetails): void |
| `email` | `?string` | Optional | The email address of the account holder. | getEmail(): ?string | setEmail(?string email): void |
| `fullPhoneNumber` | `?string` | Optional | The phone number of the account holder provided as a single string. It will be handled as a landline phone.<br>**Examples:** "0031 6 11 22 33 44", "+316/1122-3344", "(0031) 611223344" | getFullPhoneNumber(): ?string | setFullPhoneNumber(?string fullPhoneNumber): void |
| `individualDetails` | [`?IndividualDetails3`](../../doc/models/individual-details-3.md) | Optional | Details about the individual account holder.<br>Required when creating an account holder with `legalEntity` **Individual**. | getIndividualDetails(): ?IndividualDetails3 | setIndividualDetails(?IndividualDetails3 individualDetails): void |
| `lastReviewDate` | `?string` | Optional | Date when you last reviewed the account holder's information, in ISO-8601 YYYY-MM-DD format. For example, **2020-01-31**. | getLastReviewDate(): ?string | setLastReviewDate(?string lastReviewDate): void |
| `legalArrangements` | [`?(LegalArrangementDetail[])`](../../doc/models/legal-arrangement-detail.md) | Optional | An array containing information about the account holder's [legal arrangements](https://docs.adyen.com/classic-platforms/verification-process/legal-arrangements). | getLegalArrangements(): ?array | setLegalArrangements(?array legalArrangements): void |
| `merchantCategoryCode` | `?string` | Optional | The Merchant Category Code of the account holder.<br><br>> If not specified in the request, this will be derived from the platform account (which is configured by Adyen). | getMerchantCategoryCode(): ?string | setMerchantCategoryCode(?string merchantCategoryCode): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs for general use by the account holder or merchant.<br>The keys do not have specific names and may be used for storing miscellaneous data as desired.<br><br>> The values being stored have a maximum length of eighty (80) characters and will be truncated if necessary.<br>> Note that during an update of metadata, the omission of existing key-value pairs will result in the deletion of those key-value pairs. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `payoutMethods` | [`?(PayoutMethod[])`](../../doc/models/payout-method.md) | Optional | Array of tokenized card details associated with the account holder. For details about how you can use the tokens to pay out, refer to [Pay out to cards](https://docs.adyen.com/classic-platforms/payout-to-cards). | getPayoutMethods(): ?array | setPayoutMethods(?array payoutMethods): void |
| `phoneNumber` | [`?ViasPhoneNumber3`](../../doc/models/vias-phone-number-3.md) | Optional | The phone number of the account holder.<br><br>> Required if a `fullPhoneNumber` is not provided. | getPhoneNumber(): ?ViasPhoneNumber3 | setPhoneNumber(?ViasPhoneNumber3 phoneNumber): void |
| `principalBusinessAddress` | [`?ViasAddress6`](../../doc/models/vias-address-6.md) | Optional | The principal business address of the account holder. | getPrincipalBusinessAddress(): ?ViasAddress6 | setPrincipalBusinessAddress(?ViasAddress6 principalBusinessAddress): void |
| `storeDetails` | [`?(StoreDetail[])`](../../doc/models/store-detail.md) | Optional | Array of stores associated with the account holder. Required when onboarding account holders that have an Adyen [point of sale](https://docs.adyen.com/classic-platforms/platforms-for-pos). | getStoreDetails(): ?array | setStoreDetails(?array storeDetails): void |
| `webAddress` | `?string` | Optional | The URL of the website of the account holder. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderDetails2Builder;
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

$accountHolderDetails2 = AccountHolderDetails2Builder::init(
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
                ->build()
        ]
    )
    ->bankAggregatorDataReference('bankAggregatorDataReference2')
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
    ->email('email6')
    ->fullPhoneNumber('fullPhoneNumber4')
    ->build();
```

