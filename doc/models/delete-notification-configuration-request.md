
# Delete Notification Configuration Request

## Structure

`DeleteNotificationConfigurationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `notificationIds` | `int[]` | Required | A list of IDs of the notification subscription configurations to be deleted. | getNotificationIds(): array | setNotificationIds(array notificationIds): void |

## Example

```php
use AdyenLib\Models\Builders\DeleteNotificationConfigurationRequestBuilder;

$deleteNotificationConfigurationRequest = DeleteNotificationConfigurationRequestBuilder::init(
    [
        76,
        77
    ]
)->build();
```

