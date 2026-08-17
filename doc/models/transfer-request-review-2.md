
# Transfer Request Review 2

Contains information required for triggering transfer reviews.

## Structure

`TransferRequestReview2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `numberOfApprovalsRequired` | `?int` | Optional | Specifies the number of [approvals](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers/approve) required to process the transfer. | getNumberOfApprovalsRequired(): ?int | setNumberOfApprovalsRequired(?int numberOfApprovalsRequired): void |
| `scaOnApproval` | `?bool` | Optional | Specifies whether you will initiate Strong Customer Authentication (SCA) in thePOST [/transfers/approve](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers/approve) request.<br><br>Only applies to transfers made with an Adyen [business account](https://docs.adyen.com/platforms/business-accounts). | getScaOnApproval(): ?bool | setScaOnApproval(?bool scaOnApproval): void |

## Example

```php
use AdyenLib\Models\Builders\TransferRequestReview2Builder;

$transferRequestReview2 = TransferRequestReview2Builder::init()
    ->numberOfApprovalsRequired(232)
    ->scaOnApproval(false)
    ->build();
```

