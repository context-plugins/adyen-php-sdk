
# Balance Mutation

## Structure

`BalanceMutation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balance` | `?int` | Optional | The amount in the payment's currency that is debited or credited on the balance accounting register. | getBalance(): ?int | setBalance(?int balance): void |
| `currency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). | getCurrency(): ?string | setCurrency(?string currency): void |
| `received` | `?int` | Optional | The amount in the payment's currency that is debited or credited on the received accounting register. | getReceived(): ?int | setReceived(?int received): void |
| `reserved` | `?int` | Optional | The amount in the payment's currency that is debited or credited on the reserved accounting register. | getReserved(): ?int | setReserved(?int reserved): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceMutationBuilder;

$balanceMutation = BalanceMutationBuilder::init()
    ->balance(132)
    ->currency('currency8')
    ->received(50)
    ->reserved(66)
    ->build();
```

