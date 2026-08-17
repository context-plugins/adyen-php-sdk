
# Currency

## Structure

`Currency`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?int` | Optional | Surcharge amount per transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getAmount(): ?int | setAmount(?int amount): void |
| `currencyCode` | `string` | Required | Three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). For example, **AUD**. | getCurrencyCode(): string | setCurrencyCode(string currencyCode): void |
| `maxAmount` | `?int` | Optional | The maximum surcharge amount per transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getMaxAmount(): ?int | setMaxAmount(?int maxAmount): void |
| `percentage` | `?float` | Optional | Surcharge percentage per transaction. The maximum number of decimal places is two. For example, **1%** or **2.27%**. | getPercentage(): ?float | setPercentage(?float percentage): void |

## Example

```php
use AdyenLib\Models\Builders\CurrencyBuilder;

$currency = CurrencyBuilder::init(
    'currencyCode0'
)
    ->amount(158)
    ->maxAmount(148)
    ->percentage(85.58)
    ->build();
```

