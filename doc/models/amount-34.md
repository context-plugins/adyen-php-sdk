
# Amount 34

An object specifying the currency and value to which you want to convert the source amount (the target amount).

## Structure

`Amount34`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes). | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The amount of the transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount34Builder;

$amount34 = Amount34Builder::init(
    'currency6',
    48
)->build();
```

