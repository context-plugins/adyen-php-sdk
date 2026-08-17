
# Input Response 2

Content of the Input Response message.

## Structure

`InputResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `outputResult` | [`?OutputResult1`](../../doc/models/output-result-1.md) | Optional | Information related to the result the output (display, print, input).<br>If DisplayOutput present in the request. | getOutputResult(): ?OutputResult1 | setOutputResult(?OutputResult1 outputResult): void |
| `inputResult` | [`InputResult2`](../../doc/models/input-result-2.md) | Required | Contains the result and the content of the input. | getInputResult(): InputResult2 | setInputResult(InputResult2 inputResult): void |

## Example

```php
use AdyenLib\Models\Builders\InputResponse2Builder;
use AdyenLib\Models\Builders\InputResult2Builder;
use AdyenLib\Models\Device4Enum;
use AdyenLib\Models\InfoQualify2Enum;
use AdyenLib\Models\Builders\Response1Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\Input2Builder;
use AdyenLib\Models\InputCommand1Enum;
use AdyenLib\Models\Builders\OutputResult1Builder;
use AdyenLib\Models\Device3Enum;
use AdyenLib\Models\InfoQualify3Enum;
use AdyenLib\Models\Builders\Response11Builder;

$inputResponse2 = InputResponse2Builder::init(
    InputResult2Builder::init(
        Device4Enum::CASHIERDISPLAY,
        InfoQualify2Enum::INPUT,
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
        ->build()
)
    ->outputResult(
        OutputResult1Builder::init(
            Device3Enum::CASHIERINPUT,
            InfoQualify3Enum::DOCUMENT,
            Response11Builder::init(
                Result11Enum::PARTIAL
            )
                ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                ->additionalResponse('AdditionalResponse8')
                ->build()
        )->build()
    )->build();
```

