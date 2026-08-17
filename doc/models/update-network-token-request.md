
# Update Network Token Request

## Structure

`UpdateNetworkTokenRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | [`?string(Status16Enum)`](../../doc/models/status-16-enum.md) | Optional | The new status of the network token. Possible values: **active**, **suspended**, **closed**. The **closed** status is final and cannot be changed. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateNetworkTokenRequestBuilder;
use AdyenLib\Models\Status16Enum;

$updateNetworkTokenRequest = UpdateNetworkTokenRequestBuilder::init()
    ->status(Status16Enum::CLOSED)
    ->build();
```

