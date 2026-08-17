
# Migration Data 2

Details of the account holder migrated to the balance platform.

## Structure

`MigrationData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `?string` | Optional | The unique identifier of the account holder in the balance platform. | getAccountHolderId(): ?string | setAccountHolderId(?string accountHolderId): void |
| `balancePlatform` | `?string` | Optional | The unique identifier of the balance platfrom to which the account holder was migrated. | getBalancePlatform(): ?string | setBalancePlatform(?string balancePlatform): void |
| `migrated` | `?bool` | Optional | Set to **true** if the account holder has been migrated. | getMigrated(): ?bool | setMigrated(?bool migrated): void |
| `migratedAccounts` | [`?(MigratedAccounts[])`](../../doc/models/migrated-accounts.md) | Optional | Contains the mapping of virtual account codes (classic integration) to the balance account codes (balance platform) associated with the migrated account holder. | getMigratedAccounts(): ?array | setMigratedAccounts(?array migratedAccounts): void |
| `migratedShareholders` | [`?(MigratedShareholders[])`](../../doc/models/migrated-shareholders.md) | Optional | Contains the mapping of shareholders associated with the migrated legal entities. | getMigratedShareholders(): ?array | setMigratedShareholders(?array migratedShareholders): void |
| `migratedStores` | [`?(MigratedStores[])`](../../doc/models/migrated-stores.md) | Optional | Contains the mapping of business lines and stores associated with the migrated account holder. | getMigratedStores(): ?array | setMigratedStores(?array migratedStores): void |
| `migrationDate` | `?DateTime` | Optional | The date when account holder was migrated. | getMigrationDate(): ?\DateTime | setMigrationDate(?\DateTime migrationDate): void |

## Example

```php
use AdyenLib\Models\Builders\MigrationData2Builder;
use AdyenLib\Models\Builders\MigratedAccountsBuilder;
use AdyenLib\Models\Builders\MigratedShareholdersBuilder;

$migrationData2 = MigrationData2Builder::init()
    ->accountHolderId('accountHolderId8')
    ->balancePlatform('balancePlatform8')
    ->migrated(false)
    ->migratedAccounts(
        [
            MigratedAccountsBuilder::init()
                ->accountCode('accountCode6')
                ->balanceAccountId('balanceAccountId2')
                ->build(),
            MigratedAccountsBuilder::init()
                ->accountCode('accountCode6')
                ->balanceAccountId('balanceAccountId2')
                ->build(),
            MigratedAccountsBuilder::init()
                ->accountCode('accountCode6')
                ->balanceAccountId('balanceAccountId2')
                ->build()
        ]
    )
    ->migratedShareholders(
        [
            MigratedShareholdersBuilder::init()
                ->legalEntityCode('legalEntityCode0')
                ->shareholderCode('shareholderCode4')
                ->build(),
            MigratedShareholdersBuilder::init()
                ->legalEntityCode('legalEntityCode0')
                ->shareholderCode('shareholderCode4')
                ->build(),
            MigratedShareholdersBuilder::init()
                ->legalEntityCode('legalEntityCode0')
                ->shareholderCode('shareholderCode4')
                ->build()
        ]
    )
    ->build();
```

