
# Message Category Enum

Possible values:

* **Abort**
* **Admin**
* **BalanceInquiry**
* **CardAcquisition**
* **Diagnosis**
* **Display**
* **EnableService**
* **Event**
* **GetTotals**
* **Input**
* **InputUpdate**
* **Login**
* **Logout**
* **Loyalty**
* **Payment**
* **Print**
* **Reconciliation**
* **Reversal**
* **StoredValue**
* **TransactionStatus**
* **None**

## Enumeration

`MessageCategoryEnum`

## Fields

| Name |
|  --- |
| `ABORT` |
| `ADMIN` |
| `BALANCEINQUIRY` |
| `CARDACQUISITION` |
| `DIAGNOSIS` |
| `DISPLAY` |
| `ENABLESERVICE` |
| `EVENT` |
| `GETTOTALS` |
| `INPUT` |
| `INPUTUPDATE` |
| `LOGIN` |
| `LOGOUT` |
| `LOYALTY` |
| `PAYMENT` |
| `PRINT_` |
| `RECONCILIATION` |
| `REVERSAL` |
| `STOREDVALUE` |
| `TRANSACTIONSTATUS` |
| `NONE` |

## Example

```php
use AdyenLib\Models\MessageCategoryEnum;

$messageCategory = MessageCategoryEnum::ENABLESERVICE;
```

