
# Merchant Account

## Structure

`MerchantAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `inStoreTerminals` | `?(string[])` | Optional | List of terminals assigned to this merchant account as in-store terminals. This means that the terminal is ready to be boarded, or is already boarded. | getInStoreTerminals(): ?array | setInStoreTerminals(?array inStoreTerminals): void |
| `inventoryTerminals` | `?(string[])` | Optional | List of terminals assigned to the inventory of this merchant account. | getInventoryTerminals(): ?array | setInventoryTerminals(?array inventoryTerminals): void |
| `merchantAccount` | `string` | Required | The merchant account. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `stores` | [`?(Store1[])`](../../doc/models/store-1.md) | Optional | Array of stores under this merchant account. | getStores(): ?array | setStores(?array stores): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantAccountBuilder;
use AdyenLib\Models\Builders\Store1Builder;
use AdyenLib\Models\Builders\Address14Builder;

$merchantAccount = MerchantAccountBuilder::init(
    'merchantAccount0'
)
    ->inStoreTerminals(
        [
            'inStoreTerminals7'
        ]
    )
    ->inventoryTerminals(
        [
            'inventoryTerminals2',
            'inventoryTerminals3'
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
                ->build()
        ]
    )
    ->build();
```

