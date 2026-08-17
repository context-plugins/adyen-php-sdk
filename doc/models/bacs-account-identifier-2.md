
# BACS Account Identifier 2

Identifiers relevant for Bankers' Automated Clearing Services (BACS) payments, primarily used in the United Kingdom.

## Structure

`BACSAccountIdentifier2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `sortCode` | `string` | Required | A number that identifies the specific bank and branch where a UK bank account is held. | getSortCode(): string | setSortCode(string sortCode): void |

## Example

```php
use AdyenLib\Models\Builders\BACSAccountIdentifier2Builder;

$bACSAccountIdentifier2 = BACSAccountIdentifier2Builder::init(
    'accountNumber6',
    'sortCode6'
)->build();
```

