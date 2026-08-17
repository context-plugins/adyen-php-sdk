
# Approve Transfers Request

## Structure

`ApproveTransfersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferIds` | `?(string[])` | Optional | Contains the unique identifiers of the transfers that you want to approve. | getTransferIds(): ?array | setTransferIds(?array transferIds): void |

## Example

```php
use AdyenLib\Models\Builders\ApproveTransfersRequestBuilder;

$approveTransfersRequest = ApproveTransfersRequestBuilder::init()
    ->transferIds(
        [
            'transferIds6'
        ]
    )
    ->build();
```

