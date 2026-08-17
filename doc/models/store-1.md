
# Store 1

## Structure

`Store1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?Address14`](../../doc/models/address-14.md) | Optional | The address of the store. | getAddress(): ?Address14 | setAddress(?Address14 address): void |
| `description` | `?string` | Optional | The description of the store. | getDescription(): ?string | setDescription(?string description): void |
| `inStoreTerminals` | `?(string[])` | Optional | The list of terminals assigned to the store. | getInStoreTerminals(): ?array | setInStoreTerminals(?array inStoreTerminals): void |
| `merchantAccountCode` | `?string` | Optional | The code of the merchant account. | getMerchantAccountCode(): ?string | setMerchantAccountCode(?string merchantAccountCode): void |
| `status` | `?string` | Optional | The status of the store:<br><br>- `PreActive`: the store has been created, but not yet activated.<br><br>- `Active`: the store has been activated. This means you can process payments for this store.<br><br>- `Inactive`: the store is currently not active.<br><br>- `InactiveWithModifications`: the store is currently not active, but payment modifications such as refunds are possible.<br><br>- `Closed`: the store has been closed. | getStatus(): ?string | setStatus(?string status): void |
| `store` | `string` | Required | The code of the store. | getStore(): string | setStore(string store): void |

## Example

```php
use AdyenLib\Models\Builders\Store1Builder;
use AdyenLib\Models\Builders\Address14Builder;

$store1 = Store1Builder::init(
    'store4'
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
    ->description('description4')
    ->inStoreTerminals(
        [
            'inStoreTerminals9',
            'inStoreTerminals0',
            'inStoreTerminals1'
        ]
    )
    ->merchantAccountCode('merchantAccountCode8')
    ->status('status2')
    ->build();
```

