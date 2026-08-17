
# Balance Sweep Configurations Response

## Structure

`BalanceSweepConfigurationsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hasNext` | `bool` | Required | Indicates whether there are more items on the next page. | getHasNext(): bool | setHasNext(bool hasNext): void |
| `hasPrevious` | `bool` | Required | Indicates whether there are more items on the previous page. | getHasPrevious(): bool | setHasPrevious(bool hasPrevious): void |
| `sweeps` | [`SweepConfigurationV2[]`](../../doc/models/sweep-configuration-v2.md) | Required | List of sweeps associated with the balance account. | getSweeps(): array | setSweeps(array sweeps): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceSweepConfigurationsResponseBuilder;
use AdyenLib\Models\Builders\SweepConfigurationV2Builder;
use AdyenLib\Models\Builders\SweepCounterparty1Builder;
use AdyenLib\Models\Builders\SweepSchedule1Builder;
use AdyenLib\Models\Type62Enum;
use AdyenLib\Models\Category1Enum;
use AdyenLib\Models\Priority1Enum;
use AdyenLib\Models\Type72Enum;

$balanceSweepConfigurationsResponse = BalanceSweepConfigurationsResponseBuilder::init(
    false,
    false,
    [
        SweepConfigurationV2Builder::init(
            SweepCounterparty1Builder::init()
                ->balanceAccountId('balanceAccountId0')
                ->merchantAccount('merchantAccount0')
                ->transferInstrumentId('transferInstrumentId4')
                ->build(),
            'currency2',
            '',
            SweepSchedule1Builder::init(
                Type62Enum::WEEKLY
            )
                ->cronExpression('cronExpression4')
                ->build()
        )
            ->category(Category1Enum::PLATFORMPAYMENT)
            ->description('description2')
            ->priorities(
                [
                    Priority1Enum::REGULAR,
                    Priority1Enum::WIRE,
                    Priority1Enum::CROSSBORDER
                ]
            )
            ->type(Type72Enum::PUSH)
            ->build()
    ]
)->build();
```

