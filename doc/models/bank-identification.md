
# Bank Identification

## Structure

`BankIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `country` | `?string` | Optional | Two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code. | getCountry(): ?string | setCountry(?string country): void |
| `identification` | `?string` | Optional | The bank identification code. | getIdentification(): ?string | setIdentification(?string identification): void |
| `identificationType` | [`?string(IdentificationTypeEnum)`](../../doc/models/identification-type-enum.md) | Optional | The type of the identification.<br><br>Possible values: **iban**, **routingNumber**, **sortCode**, **bic**. | getIdentificationType(): ?string | setIdentificationType(?string identificationType): void |

## Example

```php
use AdyenLib\Models\Builders\BankIdentificationBuilder;
use AdyenLib\Models\IdentificationTypeEnum;

$bankIdentification = BankIdentificationBuilder::init()
    ->country('country4')
    ->identification('identification2')
    ->identificationType(IdentificationTypeEnum::ROUTINGNUMBER)
    ->build();
```

