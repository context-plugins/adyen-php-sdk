
# Duplicate Info

## Structure

`DuplicateInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `duplicateTransactionId` | `string` | Required | The transaction id associated with the duplicate charge for which you are disputing. The disputed transaction must be in the same amount as the duplicate transaction.<br><br>**Constraints**: *Minimum Length*: `1` | getDuplicateTransactionId(): string | setDuplicateTransactionId(string duplicateTransactionId): void |
| `sameCard` | `bool` | Required | The duplicate charge was made on the same card. Possible values: **true**, **false**. | getSameCard(): bool | setSameCard(bool sameCard): void |
| `sameIssuer` | `?bool` | Optional | The issuer associated with each charge is the same. Possible values: **true**, **false**. | getSameIssuer(): ?bool | setSameIssuer(?bool sameIssuer): void |

## Example

```php
use AdyenLib\Models\Builders\DuplicateInfoBuilder;

$duplicateInfo = DuplicateInfoBuilder::init(
    'duplicateTransactionId4',
    false
)
    ->sameIssuer(false)
    ->build();
```

