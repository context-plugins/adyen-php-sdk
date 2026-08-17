
# Cancel Transfers Request

## Structure

`CancelTransfersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferIds` | `?(string[])` | Optional | Contains the unique identifiers of the transfers that you want to cancel. | getTransferIds(): ?array | setTransferIds(?array transferIds): void |

## Example

```php
use AdyenLib\Models\Builders\CancelTransfersRequestBuilder;

$cancelTransfersRequest = CancelTransfersRequestBuilder::init()
    ->transferIds(
        [
            'transferIds0',
            'transferIds9',
            'transferIds8'
        ]
    )
    ->build();
```

