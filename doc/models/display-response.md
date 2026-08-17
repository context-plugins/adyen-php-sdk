
# Display Response

It conveys the result of the display, parallel to the message request, except if response not required and absent.
Content of the Display Response message.

## Structure

`DisplayResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `outputResult` | [`OutputResult[]`](../../doc/models/output-result.md) | Required | Information related to the result the output (display, print, input).<br>One per DisplayOutput item of the request, and in the same order. | getOutputResult(): array | setOutputResult(array outputResult): void |

## Example

```php
use AdyenLib\Models\Builders\DisplayResponseBuilder;
use AdyenLib\Models\Builders\OutputResultBuilder;
use AdyenLib\Models\Device3Enum;
use AdyenLib\Models\InfoQualify3Enum;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$displayResponse = DisplayResponseBuilder::init(
    [
        OutputResultBuilder::init(
            Device3Enum::CASHIERINPUT,
            InfoQualify3Enum::DOCUMENT,
            Response11Builder::init(
                Result11Enum::PARTIAL
            )
                ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                ->additionalResponse('AdditionalResponse8')
                ->build()
        )->build()
    ]
)->build();
```

