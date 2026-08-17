
# Amount 32

Required for transactions performed by registered payment facilitators. The amount of the payment corresponding to each sub-merchant. This value will be different than the request amount if shopper is purchasing items at different sub-merchants' shops.

## Structure

`Amount32`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes) of the amount.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `3` | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The numeric value of the amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount32Builder;

$amount32 = Amount32Builder::init(
    'currency0',
    206
)->build();
```

