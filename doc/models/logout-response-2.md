
# Logout Response 2

Content of the Logout Response message.

## Structure

`LogoutResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |

## Example

```php
use AdyenLib\Models\Builders\LogoutResponse2Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$logoutResponse2 = LogoutResponse2Builder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)->build();
```

