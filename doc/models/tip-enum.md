
# Tip Enum

Books the tips (gratuity) to the specified balance account.

Possible values: **addToLiableAccount**, **addToOneBalanceAccount**.

## Enumeration

`TipEnum`

## Fields

| Name |
|  --- |
| `ADDTOLIABLEACCOUNT` |
| `ADDTOONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\TipEnum;

$tip = TipEnum::ADDTOLIABLEACCOUNT;
```

