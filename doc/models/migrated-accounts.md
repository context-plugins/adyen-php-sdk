
# Migrated Accounts

## Structure

`MigratedAccounts`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `?string` | Optional | The unique identifier of the account of the migrated account holder in the classic integration. | getAccountCode(): ?string | setAccountCode(?string accountCode): void |
| `balanceAccountId` | `?string` | Optional | The unique identifier of the account of the migrated account holder in the balance platform. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |

## Example

```php
use AdyenLib\Models\Builders\MigratedAccountsBuilder;

$migratedAccounts = MigratedAccountsBuilder::init()
    ->accountCode('accountCode6')
    ->balanceAccountId('balanceAccountId2')
    ->build();
```

