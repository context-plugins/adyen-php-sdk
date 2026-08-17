
# Delete Legal Arrangement Request

## Structure

`DeleteLegalArrangementRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `legalArrangements` | [`LegalArrangementRequest[]`](../../doc/models/legal-arrangement-request.md) | Required | List of legal arrangements. | getLegalArrangements(): array | setLegalArrangements(array legalArrangements): void |

## Example

```php
use AdyenLib\Models\Builders\DeleteLegalArrangementRequestBuilder;
use AdyenLib\Models\Builders\LegalArrangementRequestBuilder;

$deleteLegalArrangementRequest = DeleteLegalArrangementRequestBuilder::init(
    'accountHolderCode2',
    [
        LegalArrangementRequestBuilder::init(
            'legalArrangementCode2'
        )
            ->legalArrangementEntityCodes(
                [
                    'legalArrangementEntityCodes8'
                ]
            )
            ->build()
    ]
)->build();
```

