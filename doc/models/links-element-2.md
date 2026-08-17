
# Links Element 2

Company account that the API credential is linked to. Only present for company-level webhooks.

## Structure

`LinksElement2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement2Builder;

$linksElement2 = LinksElement2Builder::init()
    ->href('href0')
    ->build();
```

