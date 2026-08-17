
# Get Notification Configuration Response

## Structure

`GetNotificationConfigurationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `configurationDetails` | [`NotificationConfigurationDetails2`](../../doc/models/notification-configuration-details-2.md) | Required | Details of the notification subscription configuration. | getConfigurationDetails(): NotificationConfigurationDetails2 | setConfigurationDetails(NotificationConfigurationDetails2 configurationDetails): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\GetNotificationConfigurationResponseBuilder;
use AdyenLib\Models\Builders\NotificationConfigurationDetails2Builder;
use AdyenLib\Models\Builders\NotificationEventConfigurationBuilder;
use AdyenLib\Models\EventTypeEnum;
use AdyenLib\Models\IncludeModeEnum;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$getNotificationConfigurationResponse = GetNotificationConfigurationResponseBuilder::init(
    NotificationConfigurationDetails2Builder::init()
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
                ->build(),
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
    ->pspReference('pspReference2')
    ->resultCode('resultCode4')
    ->build();
```

