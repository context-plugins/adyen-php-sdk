
# Iban Account Identification

## Structure

`IbanAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bic` | `?string` | Optional | The bank's 8- or 11-character BIC or SWIFT code. | getBic(): ?string | setBic(?string bic): void |
| `iban` | `string` | Required | The international bank account number as defined in the [ISO-13616](https://www.iso.org/standard/81090.html) standard. | getIban(): string | setIban(string iban): void |
| `type` | `string` | Required, Constant | **iban**<br><br>**Value**: `'iban'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\IbanAccountIdentificationBuilder;

$ibanAccountIdentification = IbanAccountIdentificationBuilder::init(
    'iban4'
)
    ->bic('bic2')
    ->build();
```

