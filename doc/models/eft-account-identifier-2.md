
# EFT Account Identifier 2

Identifiers relevant for Electronic Funds Transfer (EFT) payments, commonly used in Canada.

## Structure

`EFTAccountIdentifier2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `branch` | `string` | Required | Identifies the specific branch where the account is held within the Canadian banking system. | getBranch(): string | setBranch(string branch): void |
| `institution` | `string` | Required | The financial institution that identifies the bank in Canada. | getInstitution(): string | setInstitution(string institution): void |

## Example

```php
use AdyenLib\Models\Builders\EFTAccountIdentifier2Builder;

$eFTAccountIdentifier2 = EFTAccountIdentifier2Builder::init(
    'accountNumber6',
    'branch2',
    'institution6'
)->build();
```

