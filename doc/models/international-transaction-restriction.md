
# International Transaction Restriction

## Structure

`InternationalTransactionRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | Boolean indicating whether transaction is an international transaction.<br><br>Possible values:<br><br>- **true**: The transaction is an international transaction.<br><br>- **false**: The transaction is a domestic transaction. | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\InternationalTransactionRestrictionBuilder;

$internationalTransactionRestriction = InternationalTransactionRestrictionBuilder::init(
    'operation0'
)
    ->value(false)
    ->build();
```

