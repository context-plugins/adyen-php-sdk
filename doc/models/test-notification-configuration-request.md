
# Test Notification Configuration Request

## Structure

`TestNotificationConfigurationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventTypes` | [`?(string(EventType1Enum)[])`](../../doc/models/event-type-1-enum.md) | Optional | The event types to test.  If left blank, then all of the configured event types will be tested.<br><br>> Permitted values: `ACCOUNT_HOLDER_CREATED`, `ACCOUNT_CREATED`, `ACCOUNT_UPDATED`, `ACCOUNT_HOLDER_UPDATED`, `ACCOUNT_HOLDER_STATUS_CHANGE`, `ACCOUNT_HOLDER_STORE_STATUS_CHANGE` `ACCOUNT_HOLDER_VERIFICATION`, `ACCOUNT_HOLDER_LIMIT_REACHED`, `ACCOUNT_HOLDER_PAYOUT`, `PAYMENT_FAILURE`, `SCHEDULED_REFUNDS`, `REPORT_AVAILABLE`, `TRANSFER_FUNDS`, `BENEFICIARY_SETUP`, `COMPENSATE_NEGATIVE_BALANCE`. | getEventTypes(): ?array | setEventTypes(?array eventTypes): void |
| `notificationId` | `int` | Required | The ID of the notification subscription configuration to be tested. | getNotificationId(): int | setNotificationId(int notificationId): void |

## Example

```php
use AdyenLib\Models\Builders\TestNotificationConfigurationRequestBuilder;
use AdyenLib\Models\EventType1Enum;

$testNotificationConfigurationRequest = TestNotificationConfigurationRequestBuilder::init(
    134
)
    ->eventTypes(
        [
            EventType1Enum::ACCOUNT_HOLDER_UPCOMING_DEADLINE,
            EventType1Enum::ACCOUNT_HOLDER_UPDATED,
            EventType1Enum::ACCOUNT_HOLDER_VERIFICATION
        ]
    )
    ->build();
```

