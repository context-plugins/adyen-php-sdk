
# DK Local Account Identification 1

## Structure

`DKLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 4-10 digits bank account number (Kontonummer) (without separators or whitespace).<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `10` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bankCode` | `string` | Required | The 4-digit bank code (Registreringsnummer) (without separators or whitespace).<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `4` | getBankCode(): string | setBankCode(string bankCode): void |

## Example

```php
use AdyenLib\Models\Builders\DKLocalAccountIdentification1Builder;

$dKLocalAccountIdentification1 = DKLocalAccountIdentification1Builder::init(
    'accountNumber6',
    'bankCode8'
)
    ->type('dkLocal')
    ->build();
```

