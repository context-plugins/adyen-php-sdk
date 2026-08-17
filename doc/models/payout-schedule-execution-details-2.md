
# Payout Schedule Execution Details 2

Contains information about the result of the payout execution.

## Structure

`PayoutScheduleExecutionDetails2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Human readable reason for why execution was not successful if applicable. | getReason(): ?string | setReason(?string reason): void |
| `reasonCode` | `?string` | Optional | Reason Code for why execution was not successful if applicable. | getReasonCode(): ?string | setReasonCode(?string reasonCode): void |
| `transferId` | `?string` | Optional | The id of the transfer from executing the payout. | getTransferId(): ?string | setTransferId(?string transferId): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutScheduleExecutionDetails2Builder;

$payoutScheduleExecutionDetails2 = PayoutScheduleExecutionDetails2Builder::init()
    ->reason('reason8')
    ->reasonCode('reasonCode0')
    ->transferId('transferId4')
    ->build();
```

