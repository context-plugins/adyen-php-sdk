
# Acquiring Fees Enum

Deducts the acquiring fees (the aggregated amount of interchange and scheme fee) from the specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**.

## Enumeration

`AcquiringFeesEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\AcquiringFeesEnum;

$acquiringFees = AcquiringFeesEnum::DEDUCTFROMLIABLEACCOUNT;
```

