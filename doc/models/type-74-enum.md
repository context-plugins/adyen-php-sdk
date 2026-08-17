
# Type 74 Enum

The type of the source of funds.

Possible values:

* **business**
* **employment**
* **donations**
* **inheritance**
* **financialAid**
* **rentalIncome**
* **dividendIncome**
* **royaltyIncome**
* **thirdPartyFunding**
* **pensionIncome**
* **insuranceSettlement**
* **cryptocurrencyIncome**
* **assetSale**
* **loans**
* **gamblingWinnings**

## Enumeration

`Type74Enum`

## Fields

| Name |
|  --- |
| `BUSINESS` |
| `EMPLOYMENT` |
| `DONATIONS` |
| `INHERITANCE` |
| `FINANCIALAID` |
| `RENTALINCOME` |
| `DIVIDENDINCOME` |
| `ROYALTYINCOME` |
| `THIRDPARTYFUNDING` |
| `PENSIONINCOME` |
| `INSURANCESETTLEMENT` |
| `CRYPTOCURRENCYINCOME` |
| `ASSETSALE` |
| `LOANS` |
| `GAMBLINGWINNINGS` |

## Example

```php
use AdyenLib\Models\Type74Enum;

$type74 = Type74Enum::INHERITANCE;
```

