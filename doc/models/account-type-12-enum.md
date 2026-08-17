
# Account Type 12 Enum

Type of cardholder account used for the transaction. Allows a cardholder to select the type of account used for the transaction.
Possible values:

* **CardTotals**
* **Checking**
* **CreditCard**
* **Default**
* **EpurseCard**
* **Investment**
* **Savings**
* **Universal**

## Enumeration

`AccountType12Enum`

## Fields

| Name |
|  --- |
| `DEFAULT_` |
| `SAVINGS` |
| `CHECKING` |
| `CREDITCARD` |
| `UNIVERSAL` |
| `INVESTMENT` |
| `CARDTOTALS` |
| `EPURSECARD` |

## Example

```php
use AdyenLib\Models\AccountType12Enum;

$accountType12 = AccountType12Enum::CARDTOTALS;
```

