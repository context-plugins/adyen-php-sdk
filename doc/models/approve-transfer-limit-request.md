
# Approve Transfer Limit Request

## Structure

`ApproveTransferLimitRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferLimitIds` | `string[]` | Required | A list that includes the `transferLimitId` of all the pending transfer limits you want to approve.<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `2147483647` | getTransferLimitIds(): array | setTransferLimitIds(array transferLimitIds): void |

## Example

```php
use AdyenLib\Models\Builders\ApproveTransferLimitRequestBuilder;

$approveTransferLimitRequest = ApproveTransferLimitRequestBuilder::init(
    [
        'transferLimitIds8',
        'transferLimitIds9',
        'transferLimitIds0'
    ]
)->build();
```

