
# Get Terminals Under Account Response

## Structure

`GetTerminalsUnderAccountResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyAccount` | `string` | Required | Your company account. | getCompanyAccount(): string | setCompanyAccount(string companyAccount): void |
| `inventoryTerminals` | `?(string[])` | Optional | Array that returns a list of all terminals that are in the inventory of the company account. | getInventoryTerminals(): ?array | setInventoryTerminals(?array inventoryTerminals): void |
| `merchantAccounts` | [`?(MerchantAccount[])`](../../doc/models/merchant-account.md) | Optional | Array that returns a list of all merchant accounts belonging to the company account. | getMerchantAccounts(): ?array | setMerchantAccounts(?array merchantAccounts): void |

## Example

```php
use AdyenLib\Models\Builders\GetTerminalsUnderAccountResponseBuilder;
use AdyenLib\Models\Builders\MerchantAccountBuilder;
use AdyenLib\Models\Builders\Store1Builder;
use AdyenLib\Models\Builders\Address14Builder;

$getTerminalsUnderAccountResponse = GetTerminalsUnderAccountResponseBuilder::init(
    'companyAccount6'
)
    ->inventoryTerminals(
        [
            'inventoryTerminals6',
            'inventoryTerminals7'
        ]
    )
    ->merchantAccounts(
        [
            MerchantAccountBuilder::init(
                'merchantAccount2'
            )
                ->inStoreTerminals(
                    [
                        'inStoreTerminals5'
                    ]
                )
                ->inventoryTerminals(
                    [
                        'inventoryTerminals4',
                        'inventoryTerminals5'
                    ]
                )
                ->stores(
                    [
                        Store1Builder::init(
                            'store8'
                        )
                            ->address(
                                Address14Builder::init()
                                    ->city('city6')
                                    ->countryCode('countryCode8')
                                    ->postalCode('postalCode8')
                                    ->stateOrProvince('stateOrProvince4')
                                    ->streetAddress('streetAddress6')
                                    ->build()
                            )
                            ->description('description8')
                            ->inStoreTerminals(
                                [
                                    'inStoreTerminals3',
                                    'inStoreTerminals2',
                                    'inStoreTerminals1'
                                ]
                            )
                            ->merchantAccountCode('merchantAccountCode0')
                            ->status('status0')
                            ->build(),
                        Store1Builder::init(
                            'store8'
                        )
                            ->address(
                                Address14Builder::init()
                                    ->city('city6')
                                    ->countryCode('countryCode8')
                                    ->postalCode('postalCode8')
                                    ->stateOrProvince('stateOrProvince4')
                                    ->streetAddress('streetAddress6')
                                    ->build()
                            )
                            ->description('description8')
                            ->inStoreTerminals(
                                [
                                    'inStoreTerminals3',
                                    'inStoreTerminals2',
                                    'inStoreTerminals1'
                                ]
                            )
                            ->merchantAccountCode('merchantAccountCode0')
                            ->status('status0')
                            ->build(),
                        Store1Builder::init(
                            'store8'
                        )
                            ->address(
                                Address14Builder::init()
                                    ->city('city6')
                                    ->countryCode('countryCode8')
                                    ->postalCode('postalCode8')
                                    ->stateOrProvince('stateOrProvince4')
                                    ->streetAddress('streetAddress6')
                                    ->build()
                            )
                            ->description('description8')
                            ->inStoreTerminals(
                                [
                                    'inStoreTerminals3',
                                    'inStoreTerminals2',
                                    'inStoreTerminals1'
                                ]
                            )
                            ->merchantAccountCode('merchantAccountCode0')
                            ->status('status0')
                            ->build()
                    ]
                )
                ->build()
        ]
    )
    ->build();
```

