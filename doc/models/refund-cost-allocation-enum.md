
# Refund Cost Allocation Enum

Deducts the refund costs from the specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**

## Enumeration

`RefundCostAllocationEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\RefundCostAllocationEnum;

$refundCostAllocation = RefundCostAllocationEnum::DEDUCTFROMLIABLEACCOUNT;
```

