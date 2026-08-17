
# CZ Local Account Identification 1

## Structure

`CZLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 2- to 16-digit bank account number (Číslo účtu) in the following format:<br><br>- The optional prefix (předčíslí).<br><br>- The required second part (základní část) which must be at least two non-zero digits.<br><br>Examples:<br><br>- **19-123457** (with prefix)<br><br>- **123457** (without prefix)<br><br>- **000019-0000123457** (with prefix, normalized)<br><br>- **000000-0000123457** (without prefix, normalized)<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `17` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bankCode` | `string` | Required | The 4-digit bank code (Kód banky), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `4` | getBankCode(): string | setBankCode(string bankCode): void |

## Example

```php
use AdyenLib\Models\Builders\CZLocalAccountIdentification1Builder;

$cZLocalAccountIdentification1 = CZLocalAccountIdentification1Builder::init(
    'accountNumber4',
    'bankCode8'
)
    ->type('czLocal')
    ->build();
```

