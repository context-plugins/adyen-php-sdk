
# Patchable Amount DTO 1

The balance threshold that triggers the top-up. If the balance falls below this amount, a top-up is initiated.

## Structure

`PatchableAmountDTO1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). | getCurrency(): ?string | setCurrency(?string currency): void |
| `value` | `?int` | Optional | The amount of the transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getValue(): ?int | setValue(?int value): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableAmountDTO1Builder;

$patchableAmountDTO1 = PatchableAmountDTO1Builder::init()
    ->currency('currency2')
    ->value(8)
    ->build();
```

