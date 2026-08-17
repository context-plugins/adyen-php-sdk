
# Account Change Indicator Enum

Indicator for the length of time since the shopper's account was last updated.
Allowed values:

* thisTransaction
* lessThan30Days
* from30To60Days
* moreThan60Days, Indicator for the length of time since this delivery address was first used.
  Allowed values:
* thisTransaction
* lessThan30Days
* from30To60Days
* moreThan60Days

## Enumeration

`AccountChangeIndicatorEnum`

## Fields

| Name |
|  --- |
| `THISTRANSACTION` |
| `LESSTHAN30DAYS` |
| `FROM30TO60DAYS` |
| `MORETHAN60DAYS` |

## Example

```php
use AdyenLib\Models\AccountChangeIndicatorEnum;

$accountChangeIndicator = AccountChangeIndicatorEnum::FROM30TO60DAYS;
```

