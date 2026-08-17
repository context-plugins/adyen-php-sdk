
# Additional Bank Identification 1

Additional identification codes of the bank. Some banks may require these identifiers for cross-border transfers.

## Structure

`AdditionalBankIdentification1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The value of the additional bank identification. | getCode(): ?string | setCode(?string code): void |
| `type` | [`?string(Type510Enum)`](../../doc/models/type-510-enum.md) | Optional | The type of additional bank identification, depending on the country.<br><br>Possible values:<br><br>* **auBsbCode**: The 6-digit [Australian Bank State Branch (BSB) code](https://en.wikipedia.org/wiki/Bank_state_branch), without separators or spaces.<br>* **caRoutingNumber**: The 9-digit [Canadian routing number](https://en.wikipedia.org/wiki/Routing_number_(Canada)), in EFT format, without separators or spaces.<br>* **gbSortCode**: The 6-digit [UK sort code](https://en.wikipedia.org/wiki/Sort_code), without separators or spaces<br>* **usRoutingNumber**: The 9-digit [routing number](https://en.wikipedia.org/wiki/ABA_routing_transit_number), without separators or spaces. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AdditionalBankIdentification1Builder;
use AdyenLib\Models\Type510Enum;

$additionalBankIdentification1 = AdditionalBankIdentification1Builder::init()
    ->code('code4')
    ->type(Type510Enum::GBSORTCODE)
    ->build();
```

