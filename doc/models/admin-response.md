
# Admin Response

It conveys the result of the Custom Admin.
Content of the Custom Admin Response message.

## Structure

`AdminResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |

## Example

```php
use AdyenLib\Models\Builders\AdminResponseBuilder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$adminResponse = AdminResponseBuilder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)->build();
```

