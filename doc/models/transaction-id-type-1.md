
# Transaction ID Type 1

Identification of a Sale transaction.

## Structure

`TransactionIDType1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionID` | `string` | Required | Unique identification of a transaction to identify the transaction on<br>the Sale System (e.g. ticket number), or the POI System.<br><br>**Constraints**: *Pattern*: `^.+$` | getTransactionID(): string | setTransactionID(string transactionID): void |
| `timeStamp` | `DateTime` | Required | Date and time of a transaction for the Sale System, the POI System or the Acquirer.<br>Ensures the uniqueness of a transaction and indicates the time when the event<br>occurs in the EventNotification message. | getTimeStamp(): \DateTime | setTimeStamp(\DateTime timeStamp): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;

$transactionIDType1 = TransactionIDType1Builder::init(
    'TransactionID6',
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)->build();
```

