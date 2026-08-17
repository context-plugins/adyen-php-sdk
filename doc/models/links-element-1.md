
# Links Element 1

List of allowed origins.

## Structure

`LinksElement1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement1Builder;

$linksElement1 = LinksElement1Builder::init()
    ->href('href2')
    ->build();
```

