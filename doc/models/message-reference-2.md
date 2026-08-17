
# Message Reference 2

Identification of a previous POI transaction.
Present if it contains any data.

## Structure

`MessageReference2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageCategory` | [`?string(MessageCategory2Enum)`](../../doc/models/message-category-2-enum.md) | Optional | Category of message.<br>CardAcquisition, Display, Input, Loyalty, Payment, Print, CardReaderInit, CardReaderPowerOff.<br>Possible values:<br><br>* **Abort**<br>* **Admin**<br>* **BalanceInquiry**<br>* **Batch**<br>* **CardAcquisition**<br>* **CardReaderInit**<br>* **CardReaderPowerOff**<br>* **Diagnosis**<br>* **Display**<br>* **EnableService**<br>* **Event**<br>* **GetTotals**<br>* **Input**<br>* **InputUpdate**<br>* **Login**<br>* **Logout**<br>* **Loyalty**<br>* **None**<br>* **PIN**<br>* **Payment**<br>* **Print**<br>* **Reconciliation**<br>* **Reversal**<br>* **Sound**<br>* **StoredValue**<br>* **TransactionStatus**<br>* **Transmit** | getMessageCategory(): ?string | setMessageCategory(?string messageCategory): void |
| `serviceID` | `?string` | Optional | Identification of a message pair, which processes a transaction.<br><br>**Constraints**: *Pattern*: `^.{1,10}$` | getServiceID(): ?string | setServiceID(?string serviceID): void |
| `deviceID` | `?string` | Optional | Identification of a device message pair.<br><br>**Constraints**: *Pattern*: `^.{1,10}$` | getDeviceID(): ?string | setDeviceID(?string deviceID): void |
| `saleID` | `?string` | Optional | Identification of a Sale System or a Sale Terminal for the Sale to POI protocol.<br>default MessageHeader.SaleID.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleID(): ?string | setSaleID(?string saleID): void |
| `pOIID` | `?string` | Optional | Identification of a POI System or a POI Terminal for the Sale to POI protocol.<br>Default `MessageHeader.POIID`.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOIID(): ?string | setPOIID(?string pOIID): void |

## Example

```php
use AdyenLib\Models\Builders\MessageReference2Builder;
use AdyenLib\Models\MessageCategory2Enum;

$messageReference2 = MessageReference2Builder::init()
    ->messageCategory(MessageCategory2Enum::ENABLESERVICE)
    ->serviceID('ServiceID6')
    ->deviceID('DeviceID8')
    ->saleID('SaleID8')
    ->pOIID('POIID4')
    ->build();
```

