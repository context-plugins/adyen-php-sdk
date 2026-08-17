
# BSB Account Identifier 2

Identifiers relevant for Australian banking, specifically for BSB (Bank-State-Branch) numbers.

## Structure

`BSBAccountIdentifier2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bsbCode` | `string` | Required | The BSB (Bank-State-Branch) code. | getBsbCode(): string | setBsbCode(string bsbCode): void |

## Example

```php
use AdyenLib\Models\Builders\BSBAccountIdentifier2Builder;

$bSBAccountIdentifier2 = BSBAccountIdentifier2Builder::init(
    'accountNumber6',
    'bsbCode8'
)->build();
```

