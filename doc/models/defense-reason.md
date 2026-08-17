
# Defense Reason

## Structure

`DefenseReason`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defenseDocumentTypes` | [`?(DefenseDocumentType[])`](../../doc/models/defense-document-type.md) | Optional | Array of defense document types for a specific defense reason. Indicates the document types that you can submit to the schemes to defend this dispute, and whether they are required. | getDefenseDocumentTypes(): ?array | setDefenseDocumentTypes(?array defenseDocumentTypes): void |
| `defenseReasonCode` | `string` | Required | The defense reason code that was selected to defend this dispute. | getDefenseReasonCode(): string | setDefenseReasonCode(string defenseReasonCode): void |
| `satisfied` | `bool` | Required | Indicates if sufficient defense material has been supplied. | getSatisfied(): bool | setSatisfied(bool satisfied): void |

## Example

```php
use AdyenLib\Models\Builders\DefenseReasonBuilder;
use AdyenLib\Models\Builders\DefenseDocumentTypeBuilder;

$defenseReason = DefenseReasonBuilder::init(
    'defenseReasonCode2',
    false
)
    ->defenseDocumentTypes(
        [
            DefenseDocumentTypeBuilder::init(
                false,
                'defenseDocumentTypeCode0',
                'requirementLevel4'
            )->build(),
            DefenseDocumentTypeBuilder::init(
                false,
                'defenseDocumentTypeCode0',
                'requirementLevel4'
            )->build(),
            DefenseDocumentTypeBuilder::init(
                false,
                'defenseDocumentTypeCode0',
                'requirementLevel4'
            )->build()
        ]
    )->build();
```

