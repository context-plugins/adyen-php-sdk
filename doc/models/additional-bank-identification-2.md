
# Additional Bank Identification 2

## Structure

`AdditionalBankIdentification2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The value of the additional bank identification. | getCode(): ?string | setCode(?string code): void |
| `type` | [`?string(AdditionalBankIdentificationTypeEnum)`](../../doc/models/additional-bank-identification-type-enum.md) | Optional | The type of additional bank identification, depending on the country.<br><br>Possible values:<br><br>* **auBsbCode**: The 6-digit [Australian Bank State Branch (BSB) code](https://en.wikipedia.org/wiki/Bank_state_branch), without separators or spaces.<br>* **caRoutingNumber**: The 9-digit [Canadian routing number](https://en.wikipedia.org/wiki/Routing_number_(Canada)), in EFT format, without separators or spaces.<br>* **gbSortCode**: The 6-digit [UK sort code](https://en.wikipedia.org/wiki/Sort_code), without separators or spaces<br>* **usRoutingNumber**: The 9-digit [routing number](https://en.wikipedia.org/wiki/ABA_routing_transit_number), without separators or spaces. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AdditionalBankIdentification2Builder;
use AdyenLib\Models\AdditionalBankIdentificationTypeEnum;

$additionalBankIdentification2 = AdditionalBankIdentification2Builder::init()
    ->code('code2')
    ->type(AdditionalBankIdentificationTypeEnum::AUBSBCODE)
    ->build();
```

