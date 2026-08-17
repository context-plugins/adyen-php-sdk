
# IBAN Account Identifier 2

The international bank account number as defined in the ISO-13616 standard.

## Structure

`IBANAccountIdentifier2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bban` | `string` | Required | The Basic Bank Account Number (BBAN) component of the IBAN. | getBban(): string | setBban(string bban): void |
| `bic` | `string` | Required | BIC of a bank account. | getBic(): string | setBic(string bic): void |
| `iban` | `string` | Required | The international bank account number as defined in the [ISO-13616](https://www.iso.org/standard/81090.html) standard. This is the national identifier for the bank account, following the country-specific format, and is part of the full IBAN. | getIban(): string | setIban(string iban): void |

## Example

```php
use AdyenLib\Models\Builders\IBANAccountIdentifier2Builder;

$iBANAccountIdentifier2 = IBANAccountIdentifier2Builder::init(
    'bban8',
    'bic0',
    'iban2'
)->build();
```

