
# Allowed Origin

## Structure

`AllowedOrigin`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links2`](../../doc/models/links-2.md) | Optional | References to resources linked to the allowed origin. | getLinks(): ?Links2 | setLinks(?Links2 links): void |
| `domain` | `string` | Required | Domain of the allowed origin. | getDomain(): string | setDomain(string domain): void |
| `id` | `?string` | Optional | Unique identifier of the allowed origin. | getId(): ?string | setId(?string id): void |

## Example

```php
use AdyenLib\Models\Builders\AllowedOriginBuilder;
use AdyenLib\Models\Builders\Links2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;

$allowedOrigin = AllowedOriginBuilder::init(
    'https://adyen.com'
)
    ->links(
        Links2Builder::init(
            LinksElement6Builder::init()
                ->href('href0')
                ->build()
        )->build()
    )
    ->id('id0')
    ->build();
```

