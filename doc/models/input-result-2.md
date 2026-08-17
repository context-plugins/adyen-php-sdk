
# Input Result 2

Contains the result and the content of the input.

## Structure

`InputResult2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `device` | [`string(Device4Enum)`](../../doc/models/device-4-enum.md) | Required | Logical device located on a Sale Terminal or a POI Terminal, in terms of class of information to output (display, print or store), or input (keyboard) for the Cashier or the Customer.<br>Possible values:<br><br>* **CashierDisplay**<br>* **CashierInput**<br>* **CustomerDisplay**<br>* **CustomerInput** | getDevice(): string | setDevice(string device): void |
| `infoQualify` | [`string(InfoQualify2Enum)`](../../doc/models/info-qualify-2-enum.md) | Required | Qualification of the information to send to an output logical device, to display or print to the Cashier or the Customer.<br>Possible values:<br><br>* **CustomerAssistance**<br>* **Display**<br>* **Document**<br>* **Error**<br>* **Input**<br>* **POIReplication**<br>* **Receipt**<br>* **Sound**<br>* **Status**<br>* **Voucher** | getInfoQualify(): string | setInfoQualify(string infoQualify): void |
| `response` | [`Response1`](../../doc/models/response-1.md) | Required | Result of a message request processing.<br>If Result is Success, `ErrorCondition` is absent or not used in the processing of the message. In the other cases, the `ErrorCondition` has to be present and can refine the processing of the message response. `AdditionalResponse` gives more information about the success or the failure of the message request processing, for logging without real time involvements. | getResponse(): Response1 | setResponse(Response1 response): void |
| `input` | [`?Input2`](../../doc/models/input-2.md) | Optional | Data entered by the user, related to the input command. | getInput(): ?Input2 | setInput(?Input2 input): void |

## Example

```php
use AdyenLib\Models\Builders\InputResult2Builder;
use AdyenLib\Models\Device4Enum;
use AdyenLib\Models\InfoQualify2Enum;
use AdyenLib\Models\Builders\Response1Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\Input2Builder;
use AdyenLib\Models\InputCommand1Enum;

$inputResult2 = InputResult2Builder::init(
    Device4Enum::CASHIERDISPLAY,
    InfoQualify2Enum::DISPLAY,
    Response1Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)
    ->input(
        Input2Builder::init(
            InputCommand1Enum::GETMENUENTRY
        )
            ->confirmedFlag(false)
            ->functionKey(134)
            ->textInput('TextInput4')
            ->digitInput(152)
            ->password('Password0')
            ->build()
    )
    ->build();
```

