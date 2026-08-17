
# Billing Attempts Rule Enum

The rule to specify the period, within which the recurring debit can happen, relative to the mandate recurring date.

Possible values:

* **on**: On a specific date.

* **before**:  Before and on a specific date.

* **after**: On and after a specific date.

## Enumeration

`BillingAttemptsRuleEnum`

## Fields

| Name |
|  --- |
| `ON` |
| `BEFORE` |
| `AFTER` |

## Example

```php
use AdyenLib\Models\BillingAttemptsRuleEnum;

$billingAttemptsRule = BillingAttemptsRuleEnum::ON;
```

