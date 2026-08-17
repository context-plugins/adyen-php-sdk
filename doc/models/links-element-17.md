
# Links Element 17

The merchant account that the webhook is configured for. Only present for merchant-level webhooks.

## Structure

`LinksElement17`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement17Builder;

$linksElement17 = LinksElement17Builder::init()
    ->href('href8')
    ->build();
```

