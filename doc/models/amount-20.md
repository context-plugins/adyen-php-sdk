
# Amount 20

## Structure

`Amount20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO 4217 currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes).<br><br>**Constraints**: *Minimum Length*: `1` | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The amount of the transaction in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units) (cents). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount20Builder;

$amount20 = Amount20Builder::init(
    'EUR',
    499
)->build();
```

