
# Migrated Stores

## Structure

`MigratedStores`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `businessLineId` | `?string` | Optional | The unique identifier of the business line associated with the migrated account holder in the balance platform. | getBusinessLineId(): ?string | setBusinessLineId(?string businessLineId): void |
| `storeCode` | `?string` | Optional | The unique identifier of the store associated with the migrated account holder in the classic integration. | getStoreCode(): ?string | setStoreCode(?string storeCode): void |
| `storeId` | `?string` | Optional | The unique identifier of the store associated with the migrated account holder in the balance platform. | getStoreId(): ?string | setStoreId(?string storeId): void |
| `storeReference` | `?string` | Optional | Your reference for the store in the classic integration. The [Customer Area](https://ca-test.adyen.com/) uses this value for the store description. | getStoreReference(): ?string | setStoreReference(?string storeReference): void |

## Example

```php
use AdyenLib\Models\Builders\MigratedStoresBuilder;

$migratedStores = MigratedStoresBuilder::init()
    ->businessLineId('businessLineId2')
    ->storeCode('storeCode0')
    ->storeId('storeId4')
    ->storeReference('storeReference0')
    ->build();
```

