
# Pin Change Response

## Structure

`PinChangeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | [`string(Status13Enum)`](../../doc/models/status-13-enum.md) | Required | The status of the request for PIN change.<br><br>Possible values: **completed**, **pending**, **unavailable**. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\PinChangeResponseBuilder;
use AdyenLib\Models\Status13Enum;

$pinChangeResponse = PinChangeResponseBuilder::init(
    Status13Enum::COMPLETED
)->build();
```

