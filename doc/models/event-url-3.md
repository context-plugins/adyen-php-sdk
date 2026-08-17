
# Event Url 3

The list of local and public URLs to send notifications to when using local integrations.

## Structure

`EventUrl3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventLocalUrls` | [`?(Url[])`](../../doc/models/url.md) | Optional | One or more local URLs to send event notifications to when using Terminal API. | getEventLocalUrls(): ?array | setEventLocalUrls(?array eventLocalUrls): void |
| `eventPublicUrls` | [`?(Url[])`](../../doc/models/url.md) | Optional | One or more public URLs to send event notifications to when using Terminal API. | getEventPublicUrls(): ?array | setEventPublicUrls(?array eventPublicUrls): void |

## Example

```php
use AdyenLib\Models\Builders\EventUrl3Builder;
use AdyenLib\Models\Builders\UrlBuilder;

$eventUrl3 = EventUrl3Builder::init()
    ->eventLocalUrls(
        [
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
                ->build()
        ]
    )
    ->build();
```

