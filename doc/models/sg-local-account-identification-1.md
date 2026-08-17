
# SG Local Account Identification 1

## Structure

`SGLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 4- to 19-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `19` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bic` | `string` | Required | The bank's 8- or 11-character BIC or SWIFT code.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `11` | getBic(): string | setBic(string bic): void |

## Example

```php
use AdyenLib\Models\Builders\SGLocalAccountIdentification1Builder;

$sGLocalAccountIdentification1 = SGLocalAccountIdentification1Builder::init(
    'accountNumber0',
    'bic4'
)
    ->type('sgLocal')
    ->build();
```

