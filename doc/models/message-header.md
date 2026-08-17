
# Message Header

Message header of the Sale to POI protocol message.
It conveys Information related to the Sale to POI protocol management.

## Structure

`MessageHeader`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `protocolVersion` | `?string` | Optional | If MessageCategory is Login or Diagnosis.<br><br>**Constraints**: *Pattern*: `^.+$` | getProtocolVersion(): ?string | setProtocolVersion(?string protocolVersion): void |
| `messageClass` | [`string(MessageClass1Enum)`](../../doc/models/message-class-1-enum.md) | Required | Class of the message.<br>Possible values:<br><br>* **Device**<br>* **Event**<br>* **Service** | getMessageClass(): string | setMessageClass(string messageClass): void |
| `messageCategory` | [`string(MessageCategory1Enum)`](../../doc/models/message-category-1-enum.md) | Required | Category of message.<br>Possible values:<br><br>* **Abort**<br>* **Admin**<br>* **BalanceInquiry**<br>* **Batch**<br>* **CardAcquisition**<br>* **CardReaderInit**<br>* **CardReaderPowerOff**<br>* **Diagnosis**<br>* **Display**<br>* **EnableService**<br>* **Event**<br>* **GetTotals**<br>* **Input**<br>* **InputUpdate**<br>* **Login**<br>* **Logout**<br>* **Loyalty**<br>* **None**<br>* **PIN**<br>* **Payment**<br>* **Print**<br>* **Reconciliation**<br>* **Reversal**<br>* **Sound**<br>* **StoredValue**<br>* **TransactionStatus**<br>* **Transmit** | getMessageCategory(): string | setMessageCategory(string messageCategory): void |
| `messageType` | [`string(MessageType1Enum)`](../../doc/models/message-type-1-enum.md) | Required | Type of message of the Sale to POI protocol.<br>Possible values:<br><br>* **Notification**<br>* **Request**<br>* **Response** | getMessageType(): string | setMessageType(string messageType): void |
| `serviceID` | `?string` | Optional | Identification of a message pair, which processes a transaction.<br>Required if Service or Event MessageClass message or if Device MessageClass and request from POI or response from Sale.<br><br>**Constraints**: *Pattern*: `^.{1,10}$` | getServiceID(): ?string | setServiceID(?string serviceID): void |
| `deviceID` | `?string` | Optional | Identification of a device message pair.<br>If Device MessageClass.<br><br>**Constraints**: *Pattern*: `^.{1,10}$` | getDeviceID(): ?string | setDeviceID(?string deviceID): void |
| `saleID` | `string` | Required | Identification of a Sale System or a Sale Terminal for the Sale to POI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleID(): string | setSaleID(string saleID): void |
| `pOIID` | `string` | Required | Identification of a POI System or a POI Terminal for the Sale to POI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOIID(): string | setPOIID(string pOIID): void |

## Example

```php
use AdyenLib\Models\Builders\MessageHeaderBuilder;
use AdyenLib\Models\MessageClass1Enum;
use AdyenLib\Models\MessageCategory1Enum;
use AdyenLib\Models\MessageType1Enum;

$messageHeader = MessageHeaderBuilder::init(
    MessageClass1Enum::SERVICE,
    MessageCategory1Enum::PRINT_,
    MessageType1Enum::NOTIFICATION,
    'SaleID6',
    'POIID2'
)
    ->protocolVersion('ProtocolVersion0')
    ->serviceID('ServiceID4')
    ->deviceID('DeviceID6')
    ->build();
```

