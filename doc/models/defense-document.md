
# Defense Document

## Structure

`DefenseDocument`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `content` | `string` | Required | The content of the defense document. | getContent(): string | setContent(string content): void |
| `contentType` | `string` | Required | The content type of the defense document. | getContentType(): string | setContentType(string contentType): void |
| `defenseDocumentTypeCode` | `string` | Required | The document type code of the defense document. | getDefenseDocumentTypeCode(): string | setDefenseDocumentTypeCode(string defenseDocumentTypeCode): void |

## Example

```php
use AdyenLib\Models\Builders\DefenseDocumentBuilder;

$defenseDocument = DefenseDocumentBuilder::init(
    'content0',
    'contentType2',
    'defenseDocumentTypeCode6'
)->build();
```

