
# Card Brand Details

## Structure

`CardBrandDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `healthcare` | `?bool` | Optional | Indicates if the card supports FSA/HSA healthcare payments. | getHealthcare(): ?bool | setHealthcare(?bool healthcare): void |
| `supported` | `?bool` | Optional | Indicates if you support the card brand. | getSupported(): ?bool | setSupported(?bool supported): void |
| `type` | `?string` | Optional | The name of the card brand. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CardBrandDetailsBuilder;

$cardBrandDetails = CardBrandDetailsBuilder::init()
    ->healthcare(false)
    ->supported(false)
    ->type('type4')
    ->build();
```

