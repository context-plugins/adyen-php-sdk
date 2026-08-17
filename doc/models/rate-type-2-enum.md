
# Rate Type 2 Enum

The type of transaction. Possible values:

* **splitPayment**: for payments
* **splitRefund**: for refunds

## Enumeration

`RateType2Enum`

## Fields

| Name |
|  --- |
| `SPLITPAYMENT` |
| `BALANCECONVERSION` |
| `TRANSFER` |
| `SPLITREFUND` |

## Example

```php
use AdyenLib\Models\RateType2Enum;

$rateType2 = RateType2Enum::SPLITPAYMENT;
```

