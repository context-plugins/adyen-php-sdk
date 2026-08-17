
# Nexo

## Structure

`Nexo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayUrls` | [`?NotificationUrl2`](../../doc/models/notification-url-2.md) | Optional | The list of local and public URLs to send display notifications to when using Terminal API. | getDisplayUrls(): ?NotificationUrl2 | setDisplayUrls(?NotificationUrl2 displayUrls): void |
| `encryptionKey` | [`?Key1`](../../doc/models/key-1.md) | Optional | The key you share with Adyen to secure local communications when using Terminal API. | getEncryptionKey(): ?Key1 | setEncryptionKey(?Key1 encryptionKey): void |
| `eventUrls` | [`?EventUrl2`](../../doc/models/event-url-2.md) | Optional | The list of local and public URLs to send event notifications to when using Terminal API. | getEventUrls(): ?EventUrl2 | setEventUrls(?EventUrl2 eventUrls): void |
| `nexoEventUrls` | `?(string[])` | Optional | One or more URLs to send event messages to when using Terminal API. | getNexoEventUrls(): ?array | setNexoEventUrls(?array nexoEventUrls): void |
| `notification` | [`?Notification2`](../../doc/models/notification-2.md) | Optional | Configures sending event notifications by pressing a button on a terminal, for example used for pay-at-table. | getNotification(): ?Notification2 | setNotification(?Notification2 notification): void |

## Example

```php
use AdyenLib\Models\Builders\NexoBuilder;
use AdyenLib\Models\Builders\NotificationUrl2Builder;
use AdyenLib\Models\Builders\UrlBuilder;
use AdyenLib\Models\Builders\Key1Builder;
use AdyenLib\Models\Builders\EventUrl2Builder;
use AdyenLib\Models\Builders\Notification2Builder;
use AdyenLib\Models\CategoryEnum;

$nexo = NexoBuilder::init()
    ->displayUrls(
        NotificationUrl2Builder::init()
            ->localUrls(
                [
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password4')
                        ->url('url4')
                        ->username('username0')
                        ->build(),
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password4')
                        ->url('url4')
                        ->username('username0')
                        ->build(),
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password4')
                        ->url('url4')
                        ->username('username0')
                        ->build()
                ]
            )
            ->publicUrls(
                [
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password6')
                        ->url('url6')
                        ->username('username2')
                        ->build()
                ]
            )
            ->build()
    )
    ->encryptionKey(
        Key1Builder::init()
            ->identifier('identifier6')
            ->passphrase('passphrase6')
            ->version(8)
            ->build()
    )
    ->eventUrls(
        EventUrl2Builder::init()
            ->eventLocalUrls(
                [
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password4')
                        ->url('url4')
                        ->username('username0')
                        ->build(),
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password4')
                        ->url('url4')
                        ->username('username0')
                        ->build()
                ]
            )
            ->eventPublicUrls(
                [
                    UrlBuilder::init()
                        ->encrypted(false)
                        ->password('password8')
                        ->url('url8')
                        ->username('username4')
                        ->build()
                ]
            )
            ->build()
    )
    ->nexoEventUrls(
        [
            'nexoEventUrls4'
        ]
    )
    ->notification(
        Notification2Builder::init()
            ->category(CategoryEnum::SALEWAKEUP)
            ->details('details2')
            ->enabled(false)
            ->showButton(false)
            ->title('title2')
            ->build()
    )
    ->build();
```

