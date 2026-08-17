
# Links Element

The link to the first page of the list., The link to the last page of the list., The link to the next page of the list., The link to the previous page of the list., The link to the list page you are currently viewing., Contains a link to the previous page., Contains a link to the next page.

## Structure

`LinksElement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |

## Example

```php
use AdyenLib\Models\Builders\LinksElementBuilder;

$linksElement = LinksElementBuilder::init()
    ->href('href4')
    ->build();
```

