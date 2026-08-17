
# Amount 24

The cost of this delivery method.

## Structure

`Amount24`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes) of the amount.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `3` | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The numeric value of the amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount24Builder;

$amount24 = Amount24Builder::init(
    'currency2',
    62
)->build();
```

