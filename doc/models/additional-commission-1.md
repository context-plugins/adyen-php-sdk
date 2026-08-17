
# Additional Commission 1

Defines whether to book an additional commission for payments to your user's balance account. The commission amount can be defined as a fixed amount (specified in minor units), a percentage (specified in basis points), or both.

## Structure

`AdditionalCommission1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | Unique identifier of the balance account to which the additional commission is booked. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `fixedAmount` | `?int` | Optional | A fixed commission fee, in minor units. | getFixedAmount(): ?int | setFixedAmount(?int fixedAmount): void |
| `variablePercentage` | `?int` | Optional | A variable commission fee, in basis points. | getVariablePercentage(): ?int | setVariablePercentage(?int variablePercentage): void |

## Example

```php
use AdyenLib\Models\Builders\AdditionalCommission1Builder;

$additionalCommission1 = AdditionalCommission1Builder::init()
    ->balanceAccountId('balanceAccountId6')
    ->fixedAmount(204)
    ->variablePercentage(216)
    ->build();
```

