
# Account Holder Status

## Structure

`AccountHolderStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `events` | [`?(AccountEvent[])`](../../doc/models/account-event.md) | Optional | A list of events scheduled for the account holder. | getEvents(): ?array | setEvents(?array events): void |
| `payoutState` | [`?AccountPayoutState2`](../../doc/models/account-payout-state-2.md) | Optional | The payout state of the account holder. | getPayoutState(): ?AccountPayoutState2 | setPayoutState(?AccountPayoutState2 payoutState): void |
| `processingState` | [`?AccountProcessingState2`](../../doc/models/account-processing-state-2.md) | Optional | The processing state of the account holder. | getProcessingState(): ?AccountProcessingState2 | setProcessingState(?AccountProcessingState2 processingState): void |
| `status` | [`string(Status12Enum)`](../../doc/models/status-12-enum.md) | Required | The status of the account holder.<br><br>> Permitted values: `Active`, `Inactive`, `Suspended`, `Closed`. | getStatus(): string | setStatus(string status): void |
| `statusReason` | `?string` | Optional | The reason why the status was assigned to the account holder. | getStatusReason(): ?string | setStatusReason(?string statusReason): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderStatusBuilder;
use AdyenLib\Models\Status12Enum;
use AdyenLib\Models\Builders\AccountEventBuilder;
use AdyenLib\Models\EventEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AccountPayoutState2Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\AccountProcessingState2Builder;

$accountHolderStatus = AccountHolderStatusBuilder::init(
    Status12Enum::INACTIVE
)
    ->events(
        [
            AccountEventBuilder::init()
                ->event(EventEnum::INACTIVATEACCOUNT)
                ->executionDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->reason('reason6')
                ->build()
        ]
    )
    ->payoutState(
        AccountPayoutState2Builder::init()
            ->allowPayout(false)
            ->disableReason('disableReason2')
            ->disabled(false)
            ->notAllowedReason('notAllowedReason4')
            ->payoutLimit(
                AmountBuilder::init(
                    'currency8',
                    88
                )->build()
            )->build()
    )
    ->processingState(
        AccountProcessingState2Builder::init()
            ->disableReason('disableReason2')
            ->disabled(false)
            ->processedFrom(
                AmountBuilder::init(
                    'currency4',
                    148
                )->build()
            )
            ->processedTo(
                AmountBuilder::init(
                    'currency2',
                    54
                )->build()
            )
            ->tierNumber(156)
            ->build()
    )
    ->statusReason('statusReason8')
    ->build();
```

