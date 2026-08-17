
# Balance

## Structure

`Balance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `available` | `int` | Required | The balance available for use. | getAvailable(): int | setAvailable(int available): void |
| `balance` | `int` | Required | The sum of the transactions that have already been settled. | getBalance(): int | setBalance(int balance): void |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the balance. | getCurrency(): string | setCurrency(string currency): void |
| `pending` | `?int` | Optional | The sum of the transactions that will be settled in the future. | getPending(): ?int | setPending(?int pending): void |
| `pendingAvailable` | `?int` | Optional | The balance that will become the available balance after the pending balance is settled.<br><br>The pending available balance is equal to the lower of the following:<br><br>- The `pending` balance<br>- The `pending` balance plus the `available` balance. | getPendingAvailable(): ?int | setPendingAvailable(?int pendingAvailable): void |
| `reserved` | `int` | Required | The balance currently held in reserve. | getReserved(): int | setReserved(int reserved): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceBuilder;

$balance = BalanceBuilder::init(
    248,
    128,
    'currency4',
    62
)
    ->pending(56)
    ->pendingAvailable(248)
    ->build();
```

