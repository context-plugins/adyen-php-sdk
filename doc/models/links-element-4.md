
# Links Element 4

Generates a new client key, used to authenticate client-side requests. When you generate a new one, the existing key remains valid for 24 hours.

## Structure

`LinksElement4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement4Builder;

$linksElement4 = LinksElement4Builder::init()
    ->href('href8')
    ->build();
```

