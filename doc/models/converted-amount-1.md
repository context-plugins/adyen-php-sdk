
# Converted Amount 1

Amount after a currency conversion.

## Structure

`ConvertedAmount1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountValue` | `float` | Required | Value of an amount.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getAmountValue(): float | setAmountValue(float amountValue): void |
| `currency` | `string` | Required | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): string | setCurrency(string currency): void |

## Example

```php
use AdyenLib\Models\Builders\ConvertedAmount1Builder;

$convertedAmount1 = ConvertedAmount1Builder::init(
    13.36,
    'Currency4'
)->build();
```

