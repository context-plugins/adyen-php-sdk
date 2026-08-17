
# Amounts 1

The object that contains the fixed donation amounts that the shopper can select from.

## Structure

`Amounts1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes/). | getCurrency(): string | setCurrency(string currency): void |
| `values` | `int[]` | Required | The amounts of the donation (in [minor units](https://docs.adyen.com/development-resources/currency-codes/)). | getValues(): array | setValues(array values): void |

## Example

```php
use AdyenLib\Models\Builders\Amounts1Builder;

$amounts1 = Amounts1Builder::init(
    'currency6',
    [
        78,
        77
    ]
)->build();
```

