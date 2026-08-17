
# Payout Schedule Executions

## Structure

`PayoutScheduleExecutions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `payoutScheduleExecutions` | [`PayoutScheduleExecution[]`](../../doc/models/payout-schedule-execution.md) | Required | Contains a list of executions of the payout schedule. | getPayoutScheduleExecutions(): array | setPayoutScheduleExecutions(array payoutScheduleExecutions): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutScheduleExecutionsBuilder;
use AdyenLib\Models\Builders\PayoutScheduleExecutionBuilder;
use AdyenLib\Models\ExecutionResult1Enum;
use AdyenLib\Models\Builders\PayoutScheduleExecutionDetails2Builder;
use AdyenLib\Utils\DateTimeHelper;

$payoutScheduleExecutions = PayoutScheduleExecutionsBuilder::init(
    [
        PayoutScheduleExecutionBuilder::init()
            ->id('id2')
            ->result(ExecutionResult1Enum::FAILED)
            ->resultDetails(
                PayoutScheduleExecutionDetails2Builder::init()
                    ->reason('reason8')
                    ->reasonCode('reasonCode0')
                    ->transferId('transferId4')
                    ->build()
            )
            ->triggeredAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->build()
    ]
)->build();
```

