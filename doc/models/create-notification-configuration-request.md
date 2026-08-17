
# Create Notification Configuration Request

## Structure

`CreateNotificationConfigurationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `configurationDetails` | [`NotificationConfigurationDetails4`](../../doc/models/notification-configuration-details-4.md) | Required | Details of the prospective notification subscription configuration. | getConfigurationDetails(): NotificationConfigurationDetails4 | setConfigurationDetails(NotificationConfigurationDetails4 configurationDetails): void |

## Example

```php
use AdyenLib\Models\Builders\CreateNotificationConfigurationRequestBuilder;
use AdyenLib\Models\Builders\NotificationConfigurationDetails4Builder;
use AdyenLib\Models\Builders\NotificationEventConfigurationBuilder;
use AdyenLib\Models\EventTypeEnum;
use AdyenLib\Models\IncludeModeEnum;

$createNotificationConfigurationRequest = CreateNotificationConfigurationRequestBuilder::init(
    NotificationConfigurationDetails4Builder::init()
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

