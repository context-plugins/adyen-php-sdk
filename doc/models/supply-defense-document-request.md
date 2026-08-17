
# Supply Defense Document Request

## Structure

`SupplyDefenseDocumentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defenseDocuments` | [`DefenseDocument[]`](../../doc/models/defense-document.md) | Required | An array containing a list of the defense documents. | getDefenseDocuments(): array | setDefenseDocuments(array defenseDocuments): void |
| `disputePspReference` | `string` | Required | The PSP reference assigned to the dispute. | getDisputePspReference(): string | setDisputePspReference(string disputePspReference): void |
| `merchantAccountCode` | `string` | Required | The merchant account identifier, for which you want to process the dispute transaction. | getMerchantAccountCode(): string | setMerchantAccountCode(string merchantAccountCode): void |

## Example

```php
use AdyenLib\Models\Builders\SupplyDefenseDocumentRequestBuilder;
use AdyenLib\Models\Builders\DefenseDocumentBuilder;

$supplyDefenseDocumentRequest = SupplyDefenseDocumentRequestBuilder::init(
    [
        DefenseDocumentBuilder::init(
            'content0',
            'contentType2',
            'defenseDocumentTypeCode6'
        )->build()
    ],
    'disputePspReference8',
    'merchantAccountCode0'
)->build();
```

