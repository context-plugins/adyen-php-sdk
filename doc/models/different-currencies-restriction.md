
# Different Currencies Restriction

## Structure

`DifferentCurrenciesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?bool` | Optional | Checks the currency of the payment against the currency of the payment instrument.<br><br>Possible values:<br><br>- **true**: The currency of the payment is different from the currency of the payment instrument.<br><br>- **false**: The currencies are the same. | getValue(): ?bool | setValue(?bool value): void |

## Example

```php
use AdyenLib\Models\Builders\DifferentCurrenciesRestrictionBuilder;

$differentCurrenciesRestriction = DifferentCurrenciesRestrictionBuilder::init(
    'operation0'
)
    ->value(false)
    ->build();
```

