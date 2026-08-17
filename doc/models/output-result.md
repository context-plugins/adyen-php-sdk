
# Output Result

In the message response, it contains the result of the output, if required in the message request.
Information related to the result the output (display, print, input).

## Structure

`OutputResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `device` | [`string(Device3Enum)`](../../doc/models/device-3-enum.md) | Required | Logical device located on a Sale Terminal or a POI Terminal, in term of class of information to output (display, print or store), or input (keyboard) for the Cashier or the Customer.<br>Copy.<br>Possible values:<br><br>* **CashierDisplay**<br>* **CashierInput**<br>* **CustomerDisplay**<br>* **CustomerInput** | getDevice(): string | setDevice(string device): void |
| `infoQualify` | [`string(InfoQualify3Enum)`](../../doc/models/info-qualify-3-enum.md) | Required | Qualification of the information to sent to an output logical device, to display or print to the Cashier or the Customer.<br>Copy.<br>Possible values:<br><br>* **CustomerAssistance**<br>* **Display**<br>* **Document**<br>* **Error**<br>* **Input**<br>* **POIReplication**<br>* **Receipt**<br>* **Sound**<br>* **Status**<br>* **Voucher** | getInfoQualify(): string | setInfoQualify(string infoQualify): void |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |

## Example

```php
use AdyenLib\Models\Builders\OutputResultBuilder;
use AdyenLib\Models\Device3Enum;
use AdyenLib\Models\InfoQualify3Enum;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$outputResult = OutputResultBuilder::init(
    Device3Enum::CASHIERINPUT,
    InfoQualify3Enum::DOCUMENT,
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)->build();
```

