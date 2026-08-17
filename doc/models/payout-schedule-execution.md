
# Payout Schedule Execution

## Structure

`PayoutScheduleExecution`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the payout execution. | getId(): ?string | setId(?string id): void |
| `result` | [`?string(ExecutionResult1Enum)`](../../doc/models/execution-result-1-enum.md) | Optional | The status of the payout execution.<br><br>Possible values:<br><br>- **succeeded**: The payout was sent successfully.<br>- **failed**: The payout could not be sent because an error occurred.<br>- **skipped**: The payout was not triggered as expected. | getResult(): ?string | setResult(?string result): void |
| `resultDetails` | [`?PayoutScheduleExecutionDetails2`](../../doc/models/payout-schedule-execution-details-2.md) | Optional | Contains information about the result of the payout execution. | getResultDetails(): ?PayoutScheduleExecutionDetails2 | setResultDetails(?PayoutScheduleExecutionDetails2 resultDetails): void |
| `triggeredAt` | `?DateTime` | Optional | The date and time when the payout execution was initiated. | getTriggeredAt(): ?\DateTime | setTriggeredAt(?\DateTime triggeredAt): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutScheduleExecutionBuilder;
use AdyenLib\Models\ExecutionResult1Enum;
use AdyenLib\Models\Builders\PayoutScheduleExecutionDetails2Builder;
use AdyenLib\Utils\DateTimeHelper;

$payoutScheduleExecution = PayoutScheduleExecutionBuilder::init()
    ->id('id0')
    ->result(ExecutionResult1Enum::FAILED)
    ->resultDetails(
        PayoutScheduleExecutionDetails2Builder::init()
            ->reason('reason8')
            ->reasonCode('reasonCode0')
            ->transferId('transferId4')
            ->build()
    )
    ->triggeredAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

