
# Print Response 2

Content of the Print Response message.

## Structure

`PrintResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documentQualifier` | [`string(DocumentQualifier2Enum)`](../../doc/models/document-qualifier-2-enum.md) | Required | Qualification of the document to print to the Cashier or the Customer. Allows the manager of the printer, Sale or POI Terminal, to send information to a physical printer or to use the paper type accordingly.<br>Possible values:<br><br>* **CashierReceipt**<br>* **CustomerReceipt**<br>* **Document**<br>* **Journal**<br>* **SaleReceipt**<br>* **Voucher** | getDocumentQualifier(): string | setDocumentQualifier(string documentQualifier): void |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |

## Example

```php
use AdyenLib\Models\Builders\PrintResponse2Builder;
use AdyenLib\Models\DocumentQualifier2Enum;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$printResponse2 = PrintResponse2Builder::init(
    DocumentQualifier2Enum::CUSTOMERRECEIPT,
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)->build();
```

