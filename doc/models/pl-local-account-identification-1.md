
# PL Local Account Identification 1

## Structure

`PLLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 26-digit bank account number ([Numer rachunku](https://pl.wikipedia.org/wiki/Numer_Rachunku_Bankowego)), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `26`, *Maximum Length*: `26` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |

## Example

```php
use AdyenLib\Models\Builders\PLLocalAccountIdentification1Builder;

$pLLocalAccountIdentification1 = PLLocalAccountIdentification1Builder::init(
    'accountNumber4'
)
    ->type('plLocal')
    ->build();
```

