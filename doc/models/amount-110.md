
# Amount 110

The amount of the payment.

## Structure

`Amount110`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO 4217 currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes).<br><br>**Constraints**: *Minimum Length*: `1` | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The amount of the transaction in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units) (cents). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount110Builder;

$amount110 = Amount110Builder::init(
    'EUR',
    499
)->build();
```

