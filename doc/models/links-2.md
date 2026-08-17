
# Links 2

References to resources linked to the allowed origin.

## Structure

`Links2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`LinksElement6`](../../doc/models/links-element-6.md) | Required | Link to the resource itself. | getSelf(): LinksElement6 | setSelf(LinksElement6 self): void |

## Example

```php
use AdyenLib\Models\Builders\Links2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;

$links2 = Links2Builder::init(
    LinksElement6Builder::init()
        ->href('href0')
        ->build()
)->build();
```

