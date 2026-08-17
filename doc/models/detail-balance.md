
# Detail Balance

## Structure

`DetailBalance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balance` | [`?(Amount[])`](../../doc/models/amount.md) | Optional | The list of balances held by the account. | getBalance(): ?array | setBalance(?array balance): void |
| `onHoldBalance` | [`?(Amount[])`](../../doc/models/amount.md) | Optional | The list of on hold balances held by the account. | getOnHoldBalance(): ?array | setOnHoldBalance(?array onHoldBalance): void |
| `pendingBalance` | [`?(Amount[])`](../../doc/models/amount.md) | Optional | The list of pending balances held by the account. | getPendingBalance(): ?array | setPendingBalance(?array pendingBalance): void |

## Example

```php
use AdyenLib\Models\Builders\DetailBalanceBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$detailBalance = DetailBalanceBuilder::init()
    ->balance(
        [
            AmountBuilder::init(
                'currency4',
                128
            )->build(),
            AmountBuilder::init(
                'currency4',
                128
            )->build()
        ]
    )
    ->onHoldBalance(
        [
            AmountBuilder::init(
                'currency8',
                72
            )->build(),
            AmountBuilder::init(
                'currency8',
                72
            )->build(),
            AmountBuilder::init(
                'currency8',
                72
            )->build()
        ]
    )
    ->pendingBalance(
        [
            AmountBuilder::init(
                'currency2',
                254
            )->build()
        ]
    )->build();
```

