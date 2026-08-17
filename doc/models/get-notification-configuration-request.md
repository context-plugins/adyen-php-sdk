
# Get Notification Configuration Request

## Structure

`GetNotificationConfigurationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `notificationId` | `int` | Required | The ID of the notification subscription configuration whose details are to be retrieved. | getNotificationId(): int | setNotificationId(int notificationId): void |

## Example

```php
use AdyenLib\Models\Builders\GetNotificationConfigurationRequestBuilder;

$getNotificationConfigurationRequest = GetNotificationConfigurationRequestBuilder::init(
    0
)->build();
```

