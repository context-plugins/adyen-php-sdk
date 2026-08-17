
# Confirmation Tracking Data

## Structure

`ConfirmationTrackingData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | [`string(Status15Enum)`](../../doc/models/status-15-enum.md) | Required | The status of the transfer.<br><br>Possible values:<br><br>- **credited**: the funds are credited to your user's transfer instrument or bank account.- **accepted**: the request is accepted by the integration. | getStatus(): string | setStatus(string status): void |
| `type` | `string` | Required, Constant | The type of the tracking event.<br><br>Possible values:<br><br>- **confirmation**: the transfer passed Adyen's internal review.<br><br>**Value**: `'confirmation'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\ConfirmationTrackingDataBuilder;
use AdyenLib\Models\Status15Enum;

$confirmationTrackingData = ConfirmationTrackingDataBuilder::init(
    Status15Enum::CREDITED
)->build();
```

