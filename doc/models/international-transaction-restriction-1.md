
# International Transaction Restriction 1

Indicates whether transaction is an international transaction and specifies the operation.

Supported operations: **equals**, **notEquals**.

## Structure

`InternationalTransactionRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | Boolean indicating whether transaction is an international transaction.<br><br>Possible values:<br><br>- **true**: The transaction is an international transaction.<br><br>- **false**: The transaction is a domestic transaction. | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\InternationalTransactionRestriction1Builder;

$internationalTransactionRestriction1 = InternationalTransactionRestriction1Builder::init(
    'operation8'
)
    ->value(false)
    ->build();
```

