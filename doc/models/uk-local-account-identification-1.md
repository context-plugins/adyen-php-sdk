
# UK Local Account Identification 1

## Structure

`UKLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 8-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `8` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `sortCode` | `string` | Required | The 6-digit [sort code](https://en.wikipedia.org/wiki/Sort_code), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `6`, *Maximum Length*: `6` | getSortCode(): string | setSortCode(string sortCode): void |

## Example

```php
use AdyenLib\Models\Builders\UKLocalAccountIdentification1Builder;

$uKLocalAccountIdentification1 = UKLocalAccountIdentification1Builder::init(
    'accountNumber8',
    'sortCode8'
)
    ->type('ukLocal')
    ->build();
```

