
# Amount 22

The currency of the amount you converted (the source amount).

## Structure

`Amount22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes). | getCurrency(): string | setCurrency(string currency): void |
| `value` | `int` | Required | The amount of the transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes#minor-units). | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\Amount22Builder;

$amount22 = Amount22Builder::init(
    'currency2',
    148
)->build();
```

