
# Funding Source 1 Enum

The funding source of the payment method.

Possible values:

* **credit**
* **debit**
* **prepaid**
* **deferred_debit**
* **charged**
* **ANY**

## Enumeration

`FundingSource1Enum`

## Fields

| Name |
|  --- |
| `CHARGED` |
| `CREDIT` |
| `DEBIT` |
| `DEFERRED_DEBIT` |
| `PREPAID` |
| `ANY` |

## Example

```php
use AdyenLib\Models\FundingSource1Enum;

$fundingSource1 = FundingSource1Enum::CHARGED;
```

