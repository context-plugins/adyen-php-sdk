
# Paginated Account Holders Response

## Structure

`PaginatedAccountHoldersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolders` | [`AccountHolder[]`](../../doc/models/account-holder.md) | Required | List of account holders. | getAccountHolders(): array | setAccountHolders(array accountHolders): void |
| `hasNext` | `bool` | Required | Indicates whether there are more items on the next page. | getHasNext(): bool | setHasNext(bool hasNext): void |
| `hasPrevious` | `bool` | Required | Indicates whether there are more items on the previous page. | getHasPrevious(): bool | setHasPrevious(bool hasPrevious): void |

## Example

```php
use AdyenLib\Models\Builders\PaginatedAccountHoldersResponseBuilder;
use AdyenLib\Models\Builders\AccountHolderBuilder;
use AdyenLib\Models\Builders\AccountHolderCapabilityBuilder;
use AdyenLib\Models\Builders\CapabilitySettings3Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;
use AdyenLib\Models\Builders\ContactDetails1Builder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\Phone31Builder;
use AdyenLib\Models\Type410Enum;

$paginatedAccountHoldersResponse = PaginatedAccountHoldersResponseBuilder::init(
    [
        AccountHolderBuilder::init(
            '',
            'legalEntityId8'
        )
            ->balancePlatform('balancePlatform4')
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
            ->description('description2')
            ->metadata(
                [
                    'key0' => 'metadata9',
                    'key1' => 'metadata8'
                ]
            )
            ->build()
    ],
    false,
    false
)->build();
```

