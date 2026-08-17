
# BSB Account Identifier

## Structure

`BSBAccountIdentifier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bsbCode` | `string` | Required | The BSB (Bank-State-Branch) code. | getBsbCode(): string | setBsbCode(string bsbCode): void |

## Example

```php
use AdyenLib\Models\Builders\BSBAccountIdentifierBuilder;

$bSBAccountIdentifier = BSBAccountIdentifierBuilder::init(
    'accountNumber2',
    'bsbCode4'
)->build();
```

