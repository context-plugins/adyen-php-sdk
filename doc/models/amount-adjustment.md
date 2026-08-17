
# Amount Adjustment

## Structure

`AmountAdjustment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The adjustment amount. | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |
| `amountAdjustmentType` | [`?string(AmountAdjustmentTypeEnum)`](../../doc/models/amount-adjustment-type-enum.md) | Optional | The type of markup that is applied to an authorised payment.<br><br>Possible values: **exchange**, **forexMarkup**, **authHoldReserve**, **atmMarkup**. | getAmountAdjustmentType(): ?string | setAmountAdjustmentType(?string amountAdjustmentType): void |
| `basepoints` | `?int` | Optional | The basepoints associated with the applied markup. | getBasepoints(): ?int | setBasepoints(?int basepoints): void |

## Example

```php
use AdyenLib\Models\Builders\AmountAdjustmentBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\AmountAdjustmentTypeEnum;

$amountAdjustment = AmountAdjustmentBuilder::init()
    ->amount(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )
    ->amountAdjustmentType(AmountAdjustmentTypeEnum::EXCHANGE)
    ->basepoints(76)
    ->build();
```

