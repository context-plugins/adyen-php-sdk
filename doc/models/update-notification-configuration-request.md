
# Update Notification Configuration Request

## Structure

`UpdateNotificationConfigurationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `configurationDetails` | [`NotificationConfigurationDetails3`](../../doc/models/notification-configuration-details-3.md) | Required | Details of the notification subscription configuration to be updated. | getConfigurationDetails(): NotificationConfigurationDetails3 | setConfigurationDetails(NotificationConfigurationDetails3 configurationDetails): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateNotificationConfigurationRequestBuilder;
use AdyenLib\Models\Builders\NotificationConfigurationDetails3Builder;
use AdyenLib\Models\Builders\NotificationEventConfigurationBuilder;
use AdyenLib\Models\EventTypeEnum;
use AdyenLib\Models\IncludeModeEnum;

$updateNotificationConfigurationRequest = UpdateNotificationConfigurationRequestBuilder::init(
    NotificationConfigurationDetails3Builder::init()
        ->active(false)
        ->apiVersion(106)
        ->description('description6')
        ->eventConfigs(
            [
                NotificationEventConfigurationBuilder::init(
                    EventTypeEnum::SCHEDULED_REFUNDS,
                    IncludeModeEnum::EXCLUDE
                )->build(),
                NotificationEventConfigurationBuilder::init(
                    EventTypeEnum::SCHEDULED_REFUNDS,
                    IncludeModeEnum::EXCLUDE
                )->build()
            ]
        )
        ->hmacSignatureKey('hmacSignatureKey2')
        ->build()
)->build();
```

