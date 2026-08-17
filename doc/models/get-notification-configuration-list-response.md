
# Get Notification Configuration List Response

## Structure

`GetNotificationConfigurationListResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `configurations` | [`?(NotificationConfigurationDetails[])`](../../doc/models/notification-configuration-details.md) | Optional | Details of the notification subscription configurations. | getConfigurations(): ?array | setConfigurations(?array configurations): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\GetNotificationConfigurationListResponseBuilder;
use AdyenLib\Models\Builders\NotificationConfigurationDetailsBuilder;
use AdyenLib\Models\Builders\NotificationEventConfigurationBuilder;
use AdyenLib\Models\EventTypeEnum;
use AdyenLib\Models\IncludeModeEnum;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$getNotificationConfigurationListResponse = GetNotificationConfigurationListResponseBuilder::init()
    ->configurations(
        [
            NotificationConfigurationDetailsBuilder::init()
                ->active(false)
                ->apiVersion(80)
                ->description('description0')
                ->eventConfigs(
                    [
                        NotificationEventConfigurationBuilder::init(
                            EventTypeEnum::SCHEDULED_REFUNDS,
                            IncludeModeEnum::EXCLUDE
                        )->build()
                    ]
                )
                ->hmacSignatureKey('hmacSignatureKey6')
                ->build(),
            NotificationConfigurationDetailsBuilder::init()
                ->active(false)
                ->apiVersion(80)
                ->description('description0')
                ->eventConfigs(
                    [
                        NotificationEventConfigurationBuilder::init(
                            EventTypeEnum::SCHEDULED_REFUNDS,
                            IncludeModeEnum::EXCLUDE
                        )->build()
                    ]
                )
                ->hmacSignatureKey('hmacSignatureKey6')
                ->build(),
            NotificationConfigurationDetailsBuilder::init()
                ->active(false)
                ->apiVersion(80)
                ->description('description0')
                ->eventConfigs(
                    [
                        NotificationEventConfigurationBuilder::init(
                            EventTypeEnum::SCHEDULED_REFUNDS,
                            IncludeModeEnum::EXCLUDE
                        )->build()
                    ]
                )
                ->hmacSignatureKey('hmacSignatureKey6')
                ->build()
        ]
    )
    ->invalidFields(
        [
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build()
        ]
    )
    ->pspReference('pspReference8')
    ->resultCode('resultCode4')
    ->build();
```

