
# Adyen Markup Enum

Deducts the transaction fee due to Adyen under [Interchange ++ pricing](https://www.adyen.com/what-is-interchange) from the specified balance account.

Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**.

## Enumeration

`AdyenMarkupEnum`

## Fields

| Name |
|  --- |
| `DEDUCTFROMLIABLEACCOUNT` |
| `DEDUCTFROMONEBALANCEACCOUNT` |

## Example

```php
use AdyenLib\Models\AdyenMarkupEnum;

$adyenMarkup = AdyenMarkupEnum::DEDUCTFROMLIABLEACCOUNT;
```

