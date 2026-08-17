
# Card Holder PIN

## Structure

`CardHolderPIN`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `encrPINBlock` | `string` | Required | - | getEncrPINBlock(): string | setEncrPINBlock(string encrPINBlock): void |
| `pINFormat` | [`string(PINFormat1Enum)`](../../doc/models/pin-format-1-enum.md) | Required | Possible values:<br><br>* **ISO0**<br>* **ISO1**<br>* **ISO2**<br>* **ISO3** | getPINFormat(): string | setPINFormat(string pINFormat): void |
| `additionalInput` | `?string` | Optional | **Constraints**: *Pattern*: `^.+$` | getAdditionalInput(): ?string | setAdditionalInput(?string additionalInput): void |

## Example

```php
use AdyenLib\Models\Builders\CardHolderPINBuilder;
use AdyenLib\Models\PINFormat1Enum;

$cardHolderPIN = CardHolderPINBuilder::init(
    'EncrPINBlock4',
    PINFormat1Enum::ISO0
)
    ->additionalInput('AdditionalInput4')
    ->build();
```

