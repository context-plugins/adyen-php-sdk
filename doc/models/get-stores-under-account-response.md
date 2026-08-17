
# Get Stores Under Account Response

## Structure

`GetStoresUnderAccountResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `stores` | [`?(Store1[])`](../../doc/models/store-1.md) | Optional | Array that returns a list of all stores for the specified merchant account, or for all merchant accounts under the company account. | getStores(): ?array | setStores(?array stores): void |

## Example

```php
use AdyenLib\Models\Builders\GetStoresUnderAccountResponseBuilder;
use AdyenLib\Models\Builders\Store1Builder;
use AdyenLib\Models\Builders\Address14Builder;

$getStoresUnderAccountResponse = GetStoresUnderAccountResponseBuilder::init()
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
    ->build();
```

