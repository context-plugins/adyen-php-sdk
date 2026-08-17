
# Card Reader APDU Response

Content of the Card Reader APDU Response message.
It contains the result of the requested service, APDU response sent by the chip of the card in response to the APDU request.

## Structure

`CardReaderAPDUResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `aPDUData` | `?string` | Optional | Data field of the APDU command (Lc + Data).<br><br>**Constraints**: *Pattern*: `^.+$` | getAPDUData(): ?string | setAPDUData(?string aPDUData): void |
| `cardStatusWords` | `string` | Required | Status of a smartcard response to a command (SW1-SW2).<br><br>**Constraints**: *Pattern*: `^.{2,2}$` | getCardStatusWords(): string | setCardStatusWords(string cardStatusWords): void |

## Example

```php
use AdyenLib\Models\Builders\CardReaderAPDUResponseBuilder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$cardReaderAPDUResponse = CardReaderAPDUResponseBuilder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build(),
    'CardStatusWords4'
)
    ->aPDUData('APDUData8')
    ->build();
```

