
# Transfer Review 1

Contains status updates related to additional reviews.

## Structure

`TransferReview1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `numberOfApprovalsRequired` | `?int` | Optional | Shows the number of [approvals](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers/approve) required to process the transfer. | getNumberOfApprovalsRequired(): ?int | setNumberOfApprovalsRequired(?int numberOfApprovalsRequired): void |
| `scaOnApproval` | [`?string(ScaOnApprovalEnum)`](../../doc/models/sca-on-approval-enum.md) | Optional | Shows the status of the Strong Customer Authentication (SCA) process.<br><br>Possible values: **required**, **notApplicable**. | getScaOnApproval(): ?string | setScaOnApproval(?string scaOnApproval): void |

## Example

```php
use AdyenLib\Models\Builders\TransferReview1Builder;
use AdyenLib\Models\ScaOnApprovalEnum;

$transferReview1 = TransferReview1Builder::init()
    ->numberOfApprovalsRequired(128)
    ->scaOnApproval(ScaOnApprovalEnum::REQUIRED)
    ->build();
```

