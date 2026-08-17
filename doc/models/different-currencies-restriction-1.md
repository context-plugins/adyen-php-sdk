
# Different Currencies Restriction 1

Compares the currency of the payment against the currency of the payment instrument, and specifies the operation.

Supported operations: **equals**, **notEquals**.

## Structure

`DifferentCurrenciesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | Checks the currency of the payment against the currency of the payment instrument.<br><br>Possible values:<br><br>- **true**: The currency of the payment is different from the currency of the payment instrument.<br><br>- **false**: The currencies are the same. | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\DifferentCurrenciesRestriction1Builder;

$differentCurrenciesRestriction1 = DifferentCurrenciesRestriction1Builder::init(
    'operation8'
)
    ->value(false)
    ->build();
```

