
# Reversal Reason 1 Enum

Reason of the payment or loyalty reversal.
Possible values:

* **CustCancel**
* **Malfunction**
* **MerchantCancel**
* **Unable2Compl**

## Enumeration

`ReversalReason1Enum`

## Fields

| Name |
|  --- |
| `CUSTCANCEL` |
| `MERCHANTCANCEL` |
| `MALFUNCTION` |
| `UNABLE2COMPL` |

## Example

```php
use AdyenLib\Models\ReversalReason1Enum;

$reversalReason1 = ReversalReason1Enum::MALFUNCTION;
```

