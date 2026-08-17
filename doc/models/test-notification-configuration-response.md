
# Test Notification Configuration Response

## Structure

`TestNotificationConfigurationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorMessages` | `?(string[])` | Optional | Any error messages encountered. | getErrorMessages(): ?array | setErrorMessages(?array errorMessages): void |
| `eventTypes` | [`?(string(EventType1Enum)[])`](../../doc/models/event-type-1-enum.md) | Optional | The event types that were tested.<br><br>> Permitted values: `ACCOUNT_HOLDER_CREATED`, `ACCOUNT_CREATED`, `ACCOUNT_UPDATED`, `ACCOUNT_HOLDER_UPDATED`, `ACCOUNT_HOLDER_STATUS_CHANGE`, `ACCOUNT_HOLDER_STORE_STATUS_CHANGE` `ACCOUNT_HOLDER_VERIFICATION`, `ACCOUNT_HOLDER_LIMIT_REACHED`, `ACCOUNT_HOLDER_PAYOUT`, `PAYMENT_FAILURE`, `SCHEDULED_REFUNDS`, `REPORT_AVAILABLE`, `TRANSFER_FUNDS`, `BENEFICIARY_SETUP`, `COMPENSATE_NEGATIVE_BALANCE`. | getEventTypes(): ?array | setEventTypes(?array eventTypes): void |
| `exchangeMessages` | [`?(ExchangeMessage[])`](../../doc/models/exchange-message.md) | Optional | The notification message and related response messages. | getExchangeMessages(): ?array | setExchangeMessages(?array exchangeMessages): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `notificationId` | `int` | Required | The ID of the notification subscription configuration. | getNotificationId(): int | setNotificationId(int notificationId): void |
| `okMessages` | `?(string[])` | Optional | A list of messages describing the testing steps. | getOkMessages(): ?array | setOkMessages(?array okMessages): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\TestNotificationConfigurationResponseBuilder;
use AdyenLib\Models\EventType1Enum;
use AdyenLib\Models\Builders\ExchangeMessageBuilder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$testNotificationConfigurationResponse = TestNotificationConfigurationResponseBuilder::init(
    76
)
    ->errorMessages(
        [
            'errorMessages1'
        ]
    )
    ->eventTypes(
        [
            EventType1Enum::FUNDS_MIGRATED,
            EventType1Enum::PAYMENT_FAILURE
        ]
    )
    ->exchangeMessages(
        [
            ExchangeMessageBuilder::init()
                ->messageCode('messageCode8')
                ->messageDescription('messageDescription8')
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
    ->okMessages(
        [
            'okMessages0',
            'okMessages1'
        ]
    )
    ->build();
```

