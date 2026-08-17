
# BACS Account Identifier

## Structure

`BACSAccountIdentifier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `sortCode` | `string` | Required | A number that identifies the specific bank and branch where a UK bank account is held. | getSortCode(): string | setSortCode(string sortCode): void |

## Example

```php
use AdyenLib\Models\Builders\BACSAccountIdentifierBuilder;

$bACSAccountIdentifier = BACSAccountIdentifierBuilder::init(
    'accountNumber2',
    'sortCode2'
)->build();
```

