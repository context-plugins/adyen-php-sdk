
# Event Url 2

The list of local and public URLs to send event notifications to when using Terminal API.

## Structure

`EventUrl2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventLocalUrls` | [`?(Url[])`](../../doc/models/url.md) | Optional | One or more local URLs to send event notifications to when using Terminal API. | getEventLocalUrls(): ?array | setEventLocalUrls(?array eventLocalUrls): void |
| `eventPublicUrls` | [`?(Url[])`](../../doc/models/url.md) | Optional | One or more public URLs to send event notifications to when using Terminal API. | getEventPublicUrls(): ?array | setEventPublicUrls(?array eventPublicUrls): void |

## Example

```php
use AdyenLib\Models\Builders\EventUrl2Builder;
use AdyenLib\Models\Builders\UrlBuilder;

$eventUrl2 = EventUrl2Builder::init()
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
                ->build(),
            UrlBuilder::init()
                ->encrypted(false)
                ->password('password8')
                ->url('url8')
                ->username('username4')
                ->build(),
            UrlBuilder::init()
                ->encrypted(false)
                ->password('password8')
                ->url('url8')
                ->username('username4')
                ->build()
        ]
    )
    ->build();
```

