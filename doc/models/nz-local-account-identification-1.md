
# NZ Local Account Identification 1

## Structure

`NZLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 15-16 digit bank account number. The first 2 digits are the bank number, the next 4 digits are the branch number, the next 7 digits are the account number, and the final 2-3 digits are the suffix.<br><br>**Constraints**: *Minimum Length*: `15`, *Maximum Length*: `16` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |

## Example

```php
use AdyenLib\Models\Builders\NZLocalAccountIdentification1Builder;

$nZLocalAccountIdentification1 = NZLocalAccountIdentification1Builder::init(
    'accountNumber4'
)
    ->type('nzLocal')
    ->build();
```

