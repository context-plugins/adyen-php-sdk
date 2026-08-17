
# Links Element 5

The merchant account that the API credential is linked to. Only present for merchant-level API credentials.

## Structure

`LinksElement5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElement5Builder;

$linksElement5 = LinksElement5Builder::init()
    ->href('href2')
    ->build();
```

