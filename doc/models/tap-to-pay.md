
# Tap to Pay

## Structure

`TapToPay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDisplayName` | `?string` | Optional | The text shown on the screen during the Tap to Pay transaction. | getMerchantDisplayName(): ?string | setMerchantDisplayName(?string merchantDisplayName): void |

## Example

```php
use AdyenLib\Models\Builders\TapToPayBuilder;

$tapToPay = TapToPayBuilder::init()
    ->merchantDisplayName('merchantDisplayName2')
    ->build();
```

