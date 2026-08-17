
# Iban Account Identification 1

## Structure

`IbanAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bic` | `?string` | Optional | The bank's 8- or 11-character BIC or SWIFT code. | getBic(): ?string | setBic(?string bic): void |
| `iban` | `string` | Required | The international bank account number as defined in the [ISO-13616](https://www.iso.org/standard/81090.html) standard. | getIban(): string | setIban(string iban): void |

## Example

```php
use AdyenLib\Models\Builders\IbanAccountIdentification1Builder;

$ibanAccountIdentification1 = IbanAccountIdentification1Builder::init(
    'iban0'
)
    ->type('iban')
    ->bic('bic8')
    ->build();
```

