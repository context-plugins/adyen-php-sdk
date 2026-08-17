
# Adyen Fees Enum

Deducts the fees due to Adyen (markup or commission) from the specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**.

## Enumeration

`AdyenFeesEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\AdyenFeesEnum;

$adyenFees = AdyenFeesEnum::DEDUCTFROMLIABLEACCOUNT;
```

