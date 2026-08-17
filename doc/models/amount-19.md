
# Amount 19

An object specifying the currency and value for which you want to perform an exchange calculation.

## Structure

`Amount19`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes). | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The amount of the transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount19Builder;

$amount19 = Amount19Builder::init(
    'currency4',
    214
)->build();
```

