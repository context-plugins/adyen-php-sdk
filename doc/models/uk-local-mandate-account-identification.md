
# UK Local Mandate Account Identification

## Structure

`UKLocalMandateAccountIdentification`

## Inherits From

[`MandateAccountIdentification`](../../doc/models/mandate-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 8-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `8` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `sortCode` | `string` | Required | The 6-digit [sort code](https://en.wikipedia.org/wiki/Sort_code), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `6`, *Maximum Length*: `6` | getSortCode(): string | setSortCode(string sortCode): void |

## Example

```php
use AdyenLib\Models\Builders\UKLocalMandateAccountIdentificationBuilder;

$uKLocalMandateAccountIdentification = UKLocalMandateAccountIdentificationBuilder::init(
    'accountNumber4',
    'sortCode4'
)
    ->type('ukLocal')
    ->build();
```

