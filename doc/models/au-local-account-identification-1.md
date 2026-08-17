
# AU Local Account Identification 1

## Structure

`AULocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `5`, *Maximum Length*: `9` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bsbCode` | `string` | Required | The 6-digit [Bank State Branch (BSB) code](https://en.wikipedia.org/wiki/Bank_state_branch), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `6`, *Maximum Length*: `6` | getBsbCode(): string | setBsbCode(string bsbCode): void |

## Example

```php
use AdyenLib\Models\Builders\AULocalAccountIdentification1Builder;

$aULocalAccountIdentification1 = AULocalAccountIdentification1Builder::init(
    'accountNumber6',
    'bsbCode8'
)
    ->type('auLocal')
    ->build();
```

