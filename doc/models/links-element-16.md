
# Links Element 16

Generate an HMAC key.

## Structure

`LinksElement16`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement16Builder;

$linksElement16 = LinksElement16Builder::init()
    ->href('href4')
    ->build();
```

