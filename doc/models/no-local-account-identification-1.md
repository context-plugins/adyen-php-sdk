
# NO Local Account Identification 1

## Structure

`NOLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 11-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `11`, *Maximum Length*: `11` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |

## Example

```php
use AdyenLib\Models\Builders\NOLocalAccountIdentification1Builder;

$nOLocalAccountIdentification1 = NOLocalAccountIdentification1Builder::init(
    'accountNumber6'
)
    ->type('noLocal')
    ->build();
```

