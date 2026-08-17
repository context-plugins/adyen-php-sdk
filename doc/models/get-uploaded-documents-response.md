
# Get Uploaded Documents Response

## Structure

`GetUploadedDocumentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documentDetails` | [`?(DocumentDetail[])`](../../doc/models/document-detail.md) | Optional | A list of the documents and their details. | getDocumentDetails(): ?array | setDocumentDetails(?array documentDetails): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\GetUploadedDocumentsResponseBuilder;
use AdyenLib\Models\Builders\DocumentDetailBuilder;
use AdyenLib\Models\DocumentTypeEnum;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$getUploadedDocumentsResponse = GetUploadedDocumentsResponseBuilder::init()
    ->documentDetails(
        [
            DocumentDetailBuilder::init(
                DocumentTypeEnum::COMPANY_REGISTRATION_SCREENING
            )
                ->accountHolderCode('accountHolderCode0')
                ->bankAccountUUID('bankAccountUUID0')
                ->description('description4')
                ->filename('filename6')
                ->legalArrangementCode('legalArrangementCode6')
                ->build()
        ]
    )
    ->invalidFields(
        [
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build(),
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build()
        ]
    )
    ->pspReference('pspReference0')
    ->resultCode('resultCode4')
    ->build();
```

