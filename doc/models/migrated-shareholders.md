
# Migrated Shareholders

## Structure

`MigratedShareholders`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legalEntityCode` | `?string` | Optional | The unique identifier of the legal entity of that shareholder in the balance platform. | getLegalEntityCode(): ?string | setLegalEntityCode(?string legalEntityCode): void |
| `shareholderCode` | `?string` | Optional | The unique identifier of the account of the migrated shareholder in the classic integration. | getShareholderCode(): ?string | setShareholderCode(?string shareholderCode): void |

## Example

```php
use AdyenLib\Models\Builders\MigratedShareholdersBuilder;

$migratedShareholders = MigratedShareholdersBuilder::init()
    ->legalEntityCode('legalEntityCode0')
    ->shareholderCode('shareholderCode4')
    ->build();
```

