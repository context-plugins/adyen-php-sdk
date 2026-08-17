
# Remainder Enum

Books the amount left over after currency conversion to the specified balance account.

Possible values: **addToLiableAccount**, **addToOneBalanceAccount**.

## Enumeration

`RemainderEnum`

## Fields

| Name |
|  --- |
| `ADDTOLIABLEACCOUNT` |
| `ADDTOONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\RemainderEnum;

$remainder = RemainderEnum::ADDTOLIABLEACCOUNT;
```

