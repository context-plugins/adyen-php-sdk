
# Account Holder Update Request

## Structure

`AccountHolderUpdateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balancePlatform` | `?string` | Optional | The unique identifier of the [balance platform](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/get/balancePlatforms/{id}__queryParam_id) to which the account holder belongs. Required in the request if your API credentials can be used for multiple balance platforms. | getBalancePlatform(): ?string | setBalancePlatform(?string balancePlatform): void |
| `capabilities` | [`?array<string,AccountHolderCapability>`](../../doc/models/account-holder-capability.md) | Optional | Contains key-value pairs that specify the actions that an account holder can do in your platform. The key is a capability required for your integration. For example, **issueCard** for Issuing. The value is an object containing the settings for the capability. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `contactDetails` | [`?ContactDetails1`](../../doc/models/contact-details-1.md) | Optional | Contact details of the account holder. | getContactDetails(): ?ContactDetails1 | setContactDetails(?ContactDetails1 contactDetails): void |
| `description` | `?string` | Optional | Your description for the account holder.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): ?string | setDescription(?string description): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs for general use.<br>The keys do not have specific names and may be used for storing miscellaneous data as desired.<br><br>> Note that during an update of metadata, the omission of existing key-value pairs will result in the deletion of those key-value pairs. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `migratedAccountHolderCode` | `?string` | Optional, Read-only | The unique identifier of the migrated account holder in the classic integration. | getMigratedAccountHolderCode(): ?string | setMigratedAccountHolderCode(?string migratedAccountHolderCode): void |
| `primaryBalanceAccount` | `?string` | Optional | The ID of the account holder's primary balance account. By default, this is set to the first balance account that you create for the account holder. To assign a different balance account, send a PATCH request. | getPrimaryBalanceAccount(): ?string | setPrimaryBalanceAccount(?string primaryBalanceAccount): void |
| `reference` | `?string` | Optional | Your reference for the account holder.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status9Enum)`](../../doc/models/status-9-enum.md) | Optional | The status of the account holder.<br><br>Possible values:<br><br>* **active**: The account holder is active and allowed to use its capabilities. This is the initial status for account holders and balance accounts. You can change this status to **suspended** or **closed**.<br><br>* **suspended**: The account holder is temporarily disabled and payouts are blocked. You can change this status to **active** or **closed**.<br><br>* **closed**: The account holder and all of its capabilities are permanently disabled. This is a final status and cannot be changed. | getStatus(): ?string | setStatus(?string status): void |
| `timeZone` | `?string` | Optional | The time zone of the account holder. For example, **Europe/Amsterdam**.<br>Defaults to the time zone of the balance platform if no time zone is set. For possible values, see the [list of time zone codes](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). | getTimeZone(): ?string | setTimeZone(?string timeZone): void |
| `verificationDeadlines` | [`?(VerificationDeadline[])`](../../doc/models/verification-deadline.md) | Optional, Read-only | List of verification deadlines and the capabilities that will be disallowed if verification errors are not resolved. | getVerificationDeadlines(): ?array | setVerificationDeadlines(?array verificationDeadlines): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderUpdateRequestBuilder;
use AdyenLib\Models\Builders\AccountHolderCapabilityBuilder;
use AdyenLib\Models\Builders\CapabilitySettings3Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;
use AdyenLib\Models\Builders\ContactDetails1Builder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\Phone31Builder;
use AdyenLib\Models\Type410Enum;

$accountHolderUpdateRequest = AccountHolderUpdateRequestBuilder::init()
    ->balancePlatform('balancePlatform6')
    ->capabilities(
        [
            'key0' => AccountHolderCapabilityBuilder::init()
                ->allowedSettings(
                    CapabilitySettings3Builder::init()
                        ->amountPerIndustry(
                            [
                                'key0' => Amount17Builder::init(
                                    'currency8',
                                    56
                                )->build(),
                                'key1' => Amount17Builder::init(
                                    'currency8',
                                    56
                                )->build()
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
                            Amount17Builder::init(
                                'currency4',
                                160
                            )->build()
                        )->build()
                )
                ->enabled(false)
                ->build(),
            'key1' => AccountHolderCapabilityBuilder::init()
                ->allowedSettings(
                    CapabilitySettings3Builder::init()
                        ->amountPerIndustry(
                            [
                                'key0' => Amount17Builder::init(
                                    'currency8',
                                    56
                                )->build(),
                                'key1' => Amount17Builder::init(
                                    'currency8',
                                    56
                                )->build()
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
                            Amount17Builder::init(
                                'currency4',
                                160
                            )->build()
                        )->build()
                )
                ->enabled(false)
                ->build()
        ]
    )
    ->contactDetails(
        ContactDetails1Builder::init(
            AddressBuilder::init(
                'city6',
                'country0',
                'houseNumberOrName4',
                'postalCode8',
                'street6'
            )
                ->stateOrProvince('stateOrProvince4')
                ->build(),
            'email6',
            Phone31Builder::init(
                'number8',
                Type410Enum::LANDLINE
            )->build()
        )
            ->webAddress('webAddress0')
            ->build()
    )
    ->description('description4')
    ->metadata(
        [
            'key0' => 'metadata1',
            'key1' => 'metadata0'
        ]
    )
    ->build();
```

