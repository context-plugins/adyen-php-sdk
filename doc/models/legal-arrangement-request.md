
# Legal Arrangement Request

## Structure

`LegalArrangementRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legalArrangementCode` | `string` | Required | The code of the legal arrangement to be deleted. If you also send `legalArrangementEntityCodes`, only the entities listed will be deleted. | getLegalArrangementCode(): string | setLegalArrangementCode(string legalArrangementCode): void |
| `legalArrangementEntityCodes` | `?(string[])` | Optional | List of legal arrangement entities to be deleted. | getLegalArrangementEntityCodes(): ?array | setLegalArrangementEntityCodes(?array legalArrangementEntityCodes): void |

## Example

```php
use AdyenLib\Models\Builders\LegalArrangementRequestBuilder;

$legalArrangementRequest = LegalArrangementRequestBuilder::init(
    'legalArrangementCode0'
)
    ->legalArrangementEntityCodes(
        [
            'legalArrangementEntityCodes6',
            'legalArrangementEntityCodes7'
        ]
    )
    ->build();
```

