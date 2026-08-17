
# Links Element 3

Generates a new API key. When you generate a new one, the existing key remains valid for 24 hours.

## Structure

`LinksElement3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement3Builder;

$linksElement3 = LinksElement3Builder::init()
    ->href('href8')
    ->build();
```

