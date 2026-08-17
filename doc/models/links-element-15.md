
# Links Element 15

The company account that the webhook is configured for. Only present for company-level webhooks.

## Structure

`LinksElement15`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement15Builder;

$linksElement15 = LinksElement15Builder::init()
    ->href('href6')
    ->build();
```

