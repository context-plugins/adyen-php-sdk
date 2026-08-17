
# Info Qualify 3 Enum

Qualification of the information to sent to an output logical device, to display or print to the Cashier or the Customer.
Copy.
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

`InfoQualify3Enum`

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
use AdyenLib\Models\InfoQualify3Enum;

$infoQualify3 = InfoQualify3Enum::DISPLAY;
```

