
# Scheme Fee Enum

Deducts the scheme fee from the specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**.

## Enumeration

`SchemeFeeEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\SchemeFeeEnum;

$schemeFee = SchemeFeeEnum::DEDUCTFROMLIABLEACCOUNT;
```

