
# Info Qualify 2 Enum

Qualification of the information to send to an output logical device, to display or print to the Cashier or the Customer.
Possible values:

* **CustomerAssistance**
* **Display**
* **Document**
* **Error**
* **Input**
* **POIReplication**
* **Receipt**
* **Sound**
* **Status**
* **Voucher**

## Enumeration

`InfoQualify2Enum`

## Fields

| Name |
|  --- |
| `STATUS` |
| `ERROR` |
| `DISPLAY` |
| `SOUND` |
| `INPUT` |
| `POIREPLICATION` |
| `CUSTOMERASSISTANCE` |
| `RECEIPT` |
| `DOCUMENT` |
| `VOUCHER` |

## Example

```php
use AdyenLib\Models\InfoQualify2Enum;

$infoQualify2 = InfoQualify2Enum::STATUS;
```

