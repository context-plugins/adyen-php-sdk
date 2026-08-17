
# Patchable Amount DTO

Required if `type` is **business**, **assetSale**, **gamblingWinnings** or **inheritance**.

For `type` **business**, provide the annual turn over of the business. For `type` **assetSale**, **gamblingWinnings** or **inheritance**, provide the amount of the funds., The amount of the funds the financier provided., The maximum amount a card holder can withdraw per day.

## Structure

`PatchableAmountDTO`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). | getCurrency(): ?string | setCurrency(?string currency): void |
| `value` | `?int` | Optional | The amount of the transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;

$patchableAmountDTO = PatchableAmountDTOBuilder::init()
    ->currency('currency8')
    ->value(166)
    ->build();
```

