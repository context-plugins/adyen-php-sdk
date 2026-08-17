
# Notification Configuration Details 2

Details of the notification subscription configuration.

## Structure

`NotificationConfigurationDetails2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `active` | `?bool` | Optional | Indicates whether the notification subscription is active. | getActive(): ?bool | setActive(?bool active): void |
| `apiVersion` | `?int` | Optional | The version of the notification to which you are subscribing. To make sure that your integration can properly process the notification, subscribe to the same version as the API that you're using. | getApiVersion(): ?int | setApiVersion(?int apiVersion): void |
| `description` | `?string` | Optional | A description of the notification subscription configuration. | getDescription(): ?string | setDescription(?string description): void |
| `eventConfigs` | [`?(NotificationEventConfiguration[])`](../../doc/models/notification-event-configuration.md) | Optional | Contains objects that define event types and their subscription settings. | getEventConfigs(): ?array | setEventConfigs(?array eventConfigs): void |
| `hmacSignatureKey` | `?string` | Optional | A string with which to salt the notification(s) before hashing. If this field is provided, a hash value will be included under the notification header `HmacSignature` and the hash protocol will be included under the notification header `Protocol`. A notification body along with its `hmacSignatureKey` and `Protocol` can be used to calculate a hash value; matching this hash value with the `HmacSignature` will ensure that the notification body has not been tampered with or corrupted.<br><br>> Must be a 32-byte hex-encoded string (i.e. a string containing 64 hexadecimal characters; e.g. "b0ea55c2fe60d4d1d605e9c385e0e7f7e6cafbb939ce07010f31a327a0871f27").<br><br>The omission of this field will preclude the provision of the `HmacSignature` and `Protocol` headers in notification(s). | getHmacSignatureKey(): ?string | setHmacSignatureKey(?string hmacSignatureKey): void |
| `notificationId` | `?int` | Optional | Adyen-generated ID for the entry, returned in the response when you create a notification configuration. Required when updating an existing configuration using [`/updateNotificationConfiguration`](https://docs.adyen.com/api-explorer/#/NotificationConfigurationService/latest/post/updateNotificationConfiguration). | getNotificationId(): ?int | setNotificationId(?int notificationId): void |
| `notifyPassword` | `?string` | Optional | The password to use when accessing the notifyURL with the specified username. | getNotifyPassword(): ?string | setNotifyPassword(?string notifyPassword): void |
| `notifyURL` | `?string` | Optional | The URL to which the notifications are to be sent. | getNotifyURL(): ?string | setNotifyURL(?string notifyURL): void |
| `notifyUsername` | `?string` | Optional | The username to use when accessing the notifyURL. | getNotifyUsername(): ?string | setNotifyUsername(?string notifyUsername): void |
| `sslProtocol` | [`?string(SslProtocolEnum)`](../../doc/models/ssl-protocol-enum.md) | Optional | The SSL protocol employed by the endpoint.<br><br>> Permitted values: `TLSv12`, `TLSv13`. | getSslProtocol(): ?string | setSslProtocol(?string sslProtocol): void |

## Example

```php
use AdyenLib\Models\Builders\NotificationConfigurationDetails2Builder;
use AdyenLib\Models\Builders\NotificationEventConfigurationBuilder;
use AdyenLib\Models\EventTypeEnum;
use AdyenLib\Models\IncludeModeEnum;

$notificationConfigurationDetails2 = NotificationConfigurationDetails2Builder::init()
    ->active(false)
    ->apiVersion(100)
    ->description('description4')
    ->eventConfigs(
        [
            NotificationEventConfigurationBuilder::init(
                EventTypeEnum::SCHEDULED_REFUNDS,
                IncludeModeEnum::EXCLUDE
            )->build(),
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
    ->hmacSignatureKey('hmacSignatureKey0')
    ->build();
```

