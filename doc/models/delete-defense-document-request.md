
# Delete Defense Document Request

## Structure

`DeleteDefenseDocumentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defenseDocumentType` | `string` | Required | The document type code of the defense document. | getDefenseDocumentType(): string | setDefenseDocumentType(string defenseDocumentType): void |
| `disputePspReference` | `string` | Required | The PSP reference assigned to the dispute. | getDisputePspReference(): string | setDisputePspReference(string disputePspReference): void |
| `merchantAccountCode` | `string` | Required | The merchant account identifier, for which you want to process the dispute transaction. | getMerchantAccountCode(): string | setMerchantAccountCode(string merchantAccountCode): void |

## Example

```php
use AdyenLib\Models\Builders\DeleteDefenseDocumentRequestBuilder;

$deleteDefenseDocumentRequest = DeleteDefenseDocumentRequestBuilder::init(
    'defenseDocumentType4',
    'disputePspReference6',
    'merchantAccountCode8'
)->build();
```

