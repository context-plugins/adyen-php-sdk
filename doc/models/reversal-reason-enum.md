
# Reversal Reason Enum

Reason of the payment or loyalty reversal.
Possible values:

* **CustCancel**
* **MerchantCancel**
* **Malfunction**
* **Unable2Compl**

## Enumeration

`ReversalReasonEnum`

## Fields

| Name |
|  --- |
| `CUSTCANCEL` |
| `MERCHANTCANCEL` |
| `MALFUNCTION` |
| `UNABLE2COMPL` |

## Example

```php
use AdyenLib\Models\ReversalReasonEnum;

$reversalReason = ReversalReasonEnum::CUSTCANCEL;
```

