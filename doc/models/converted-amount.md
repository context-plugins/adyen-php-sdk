
# Converted Amount

## Structure

`ConvertedAmount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountValue` | `float` | Required | Value of an amount.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getAmountValue(): float | setAmountValue(float amountValue): void |
| `currency` | `string` | Required | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): string | setCurrency(string currency): void |

## Example

```php
use AdyenLib\Models\Builders\ConvertedAmountBuilder;

$convertedAmount = ConvertedAmountBuilder::init(
    232.7,
    'Currency8'
)->build();
```

