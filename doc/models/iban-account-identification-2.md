
# Iban Account Identification 2

## Structure

`IbanAccountIdentification2`

## Inherits From

[`AccountIdentification`](../../doc/models/account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iban` | `string` | Required | The IBAN of the bank account.<br><br>**Constraints**: *Minimum Length*: `1` | getIban(): string | setIban(string iban): void |

## Example

```php
use AdyenLib\Models\Builders\IbanAccountIdentification2Builder;

$ibanAccountIdentification2 = IbanAccountIdentification2Builder::init(
    'NL00AAAA0000000000'
)
    ->type('iban')
    ->build();
```

