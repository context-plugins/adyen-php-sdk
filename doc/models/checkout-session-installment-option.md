
# Checkout Session Installment Option

## Structure

`CheckoutSessionInstallmentOption`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `plans` | [`?(string(Plan1Enum)[])`](../../doc/models/plan-1-enum.md) | Optional | Defines the type of installment plan. If not set, defaults to **regular**.<br><br>Possible values:<br><br>* **regular**<br>* **revolving**<br>* **bonus**<br>* **with_interest**<br>* **buynow_paylater**<br>* **nointerest_bonus**<br>* **interest_bonus**<br>* **refund_prctg**<br>* **nointeres_refund_prctg**<br>* **interes_refund_prctg** | getPlans(): ?array | setPlans(?array plans): void |
| `preselectedValue` | `?int` | Optional | Preselected number of installments offered for this payment method. | getPreselectedValue(): ?int | setPreselectedValue(?int preselectedValue): void |
| `values` | `?(int[])` | Optional | An array of the number of installments that the shopper can choose from. For example, **[2,3,5]**. This cannot be specified simultaneously with `maxValue`. | getValues(): ?array | setValues(?array values): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutSessionInstallmentOptionBuilder;
use AdyenLib\Models\Plan1Enum;

$checkoutSessionInstallmentOption = CheckoutSessionInstallmentOptionBuilder::init()
    ->plans(
        [
            Plan1Enum::INTEREST_BONUS
        ]
    )
    ->preselectedValue(124)
    ->values(
        [
            58,
            57,
            56
        ]
    )
    ->build();
```

