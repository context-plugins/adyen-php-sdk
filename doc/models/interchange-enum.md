
# Interchange Enum

Deducts the interchange fee from specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**.

## Enumeration

`InterchangeEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\InterchangeEnum;

$interchange = InterchangeEnum::DEDUCTFROMLIABLEACCOUNT;
```

