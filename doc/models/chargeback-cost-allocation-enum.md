
# Chargeback Cost Allocation Enum

Deducts the chargeback costs from the specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**

## Enumeration

`ChargebackCostAllocationEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\ChargebackCostAllocationEnum;

$chargebackCostAllocation = ChargebackCostAllocationEnum::DEDUCTFROMLIABLEACCOUNT;
```

