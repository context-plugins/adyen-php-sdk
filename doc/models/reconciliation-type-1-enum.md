
# Reconciliation Type 1 Enum

Type of Reconciliation requested by the Sale to the POI.
Possible values:

* **AcquirerReconciliation**
* **AcquirerSynchronisation**
* **PreviousReconciliation**
* **SaleReconciliation**

## Enumeration

`ReconciliationType1Enum`

## Fields

| Name |
|  --- |
| `SALERECONCILIATION` |
| `ACQUIRERSYNCHRONISATION` |
| `ACQUIRERRECONCILIATION` |
| `PREVIOUSRECONCILIATION` |

## Example

```php
use AdyenLib\Models\ReconciliationType1Enum;

$reconciliationType1 = ReconciliationType1Enum::SALERECONCILIATION;
```

