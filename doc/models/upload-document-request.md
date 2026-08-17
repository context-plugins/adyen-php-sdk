
# Upload Document Request

## Structure

`UploadDocumentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documentContent` | `string` | Required | The content of the document, in Base64-encoded string format.<br><br>To learn about document requirements, refer to [Verification checks](https://docs.adyen.com/classic-platforms/verification-checks). | getDocumentContent(): string | setDocumentContent(string documentContent): void |
| `documentDetail` | [`DocumentDetail1`](../../doc/models/document-detail-1.md) | Required | Details of the document being submitted. | getDocumentDetail(): DocumentDetail1 | setDocumentDetail(DocumentDetail1 documentDetail): void |

## Example

```php
use AdyenLib\Models\Builders\UploadDocumentRequestBuilder;
use AdyenLib\Models\Builders\DocumentDetail1Builder;
use AdyenLib\Models\DocumentTypeEnum;

$uploadDocumentRequest = UploadDocumentRequestBuilder::init(
    'documentContent8',
    DocumentDetail1Builder::init(
        DocumentTypeEnum::SSN
    )
        ->accountHolderCode('accountHolderCode0')
        ->bankAccountUUID('bankAccountUUID0')
        ->description('description6')
        ->filename('filename6')
        ->legalArrangementCode('legalArrangementCode6')
        ->build()
)->build();
```

