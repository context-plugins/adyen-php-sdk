
# Tax Information

## Structure

`TaxInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `country` | `?string` | Optional | The two-letter [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `number` | `?string` | Optional | The tax ID number (TIN) of the organization or individual. | getNumber(): ?string | setNumber(?string number): void |
| `numberAbsent` | `?bool` | Optional | Set this to **true** if the legal entity or legal arrangement does not have a tax ID number (TIN). Only applicable in Australia. | getNumberAbsent(): ?bool | setNumberAbsent(?bool numberAbsent): void |
| `type` | `?string` | Optional | The TIN type depending on the country where it was issued. Only provide if the country has multiple tax IDs: Singapore, Sweden, the UK, or the US. For example, provide **SSN**, **EIN**, or **ITIN** for the US. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\TaxInformationBuilder;

$taxInformation = TaxInformationBuilder::init()
    ->country('country4')
    ->number('number2')
    ->numberAbsent(false)
    ->type('type0')
    ->build();
```

