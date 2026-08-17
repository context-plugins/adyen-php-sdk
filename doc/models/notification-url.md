
# Notification Url

## Structure

`NotificationUrl`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `localUrls` | [`?(Url[])`](../../doc/models/url.md) | Optional | One or more local URLs to send notifications to when using Terminal API. | getLocalUrls(): ?array | setLocalUrls(?array localUrls): void |
| `publicUrls` | [`?(Url[])`](../../doc/models/url.md) | Optional | One or more public URLs to send notifications to when using Terminal API. | getPublicUrls(): ?array | setPublicUrls(?array publicUrls): void |

## Example

```php
use AdyenLib\Models\Builders\NotificationUrlBuilder;
use AdyenLib\Models\Builders\UrlBuilder;

$notificationUrl = NotificationUrlBuilder::init()
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
                ->build(),
            UrlBuilder::init()
                ->encrypted(false)
                ->password('password6')
                ->url('url6')
                ->username('username2')
                ->build()
        ]
    )
    ->build();
```

