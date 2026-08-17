
# Account Type 4 Enum

Type of cardholder account used for the transaction. Allows a cardholder to select the type of account used for the transaction.
Possible values:

* **Default**
* **Savings**
* **Checking**
* **CreditCard**
* **Universal**
* **Investment**
* **CardTotals**
* **EpurseCard**

## Enumeration

`AccountType4Enum`

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
use AdyenLib\Models\AccountType4Enum;

$accountType4 = AccountType4Enum::UNIVERSAL;
```

