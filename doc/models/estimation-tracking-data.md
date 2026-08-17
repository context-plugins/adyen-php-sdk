
# Estimation Tracking Data

## Structure

`EstimationTrackingData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `estimatedArrivalTime` | `DateTime` | Required | The estimated time the beneficiary should have access to the funds. | getEstimatedArrivalTime(): \DateTime | setEstimatedArrivalTime(\DateTime estimatedArrivalTime): void |
| `type` | `string` | Required, Constant | The type of tracking event.<br><br>Possible values:<br><br>- **estimation**: the estimated date and time of when the funds will be credited has been determined.<br><br>**Value**: `'estimation'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\EstimationTrackingDataBuilder;
use AdyenLib\Utils\DateTimeHelper;

$estimationTrackingData = EstimationTrackingDataBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)->build();
```

