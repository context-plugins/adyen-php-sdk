
# Amount Adjustment Type Enum

The type of markup that is applied to an authorised payment.

Possible values: **exchange**, **forexMarkup**, **authHoldReserve**, **atmMarkup**.

## Enumeration

`AmountAdjustmentTypeEnum`

## Fields

| Name |
|  --- |
| `ATMMARKUP` |
| `AUTHHOLDRESERVE` |
| `EXCHANGE` |
| `FOREXMARKUP` |

## Example

```php
use AdyenLib\Models\AmountAdjustmentTypeEnum;

$amountAdjustmentType = AmountAdjustmentTypeEnum::ATMMARKUP;
```

