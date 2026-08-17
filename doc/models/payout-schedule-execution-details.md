
# Payout Schedule Execution Details

## Structure

`PayoutScheduleExecutionDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Human readable reason for why execution was not successful if applicable. | getReason(): ?string | setReason(?string reason): void |
| `reasonCode` | `?string` | Optional | Reason Code for why execution was not successful if applicable. | getReasonCode(): ?string | setReasonCode(?string reasonCode): void |
| `transferId` | `?string` | Optional | The id of the transfer from executing the payout. | getTransferId(): ?string | setTransferId(?string transferId): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutScheduleExecutionDetailsBuilder;

$payoutScheduleExecutionDetails = PayoutScheduleExecutionDetailsBuilder::init()
    ->reason('reason4')
    ->reasonCode('reasonCode2')
    ->transferId('transferId6')
    ->build();
```

