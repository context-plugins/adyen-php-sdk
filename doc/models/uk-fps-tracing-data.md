
# UK Fps Tracing Data

## Structure

`UKFpsTracingData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fpid` | `string` | Required | The FPS trace number. This is a unique identifier assigned to transfers processed by [FPS](https://www.bankofengland.co.uk/payment-systems/services/faster-payments-service). | getFpid(): string | setFpid(string fpid): void |
| `type` | `string` | Required, Constant | **ukFps**<br><br>**Value**: `'ukFps'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\UKFpsTracingDataBuilder;

$uKFpsTracingData = UKFpsTracingDataBuilder::init(
    'fpid0'
)->build();
```

