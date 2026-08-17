
# Message Category 1 Enum

Category of message.
Possible values:

* **Abort**
* **Admin**
* **BalanceInquiry**
* **Batch**
* **CardAcquisition**
* **CardReaderInit**
* **CardReaderPowerOff**
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
* **None**
* **PIN**
* **Payment**
* **Print**
* **Reconciliation**
* **Reversal**
* **Sound**
* **StoredValue**
* **TransactionStatus**
* **Transmit**

## Enumeration

`MessageCategory1Enum`

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
use AdyenLib\Models\MessageCategory1Enum;

$messageCategory1 = MessageCategory1Enum::REVERSAL;
```

