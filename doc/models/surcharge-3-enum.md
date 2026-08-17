
# Surcharge 3 Enum

Books the surcharge amount to the specified balance account.

Possible values: **addToLiableAccount**, **addToOneBalanceAccount**

## Enumeration

`Surcharge3Enum`

## Fields

| Name |
|  --- |
| `ADDTOLIABLEACCOUNT` |
| `ADDTOONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\Surcharge3Enum;

$surcharge3 = Surcharge3Enum::ADDTOLIABLEACCOUNT;
```

